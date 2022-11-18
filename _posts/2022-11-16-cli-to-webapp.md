---
layout: post
title:  "cli2web"
comments: true
date:   2022-11-16
---

I'd love to start building a Transformer that takes the code of a CLI tool (start with just Python) and then automatically generate an HTML + CSS + JavaScript UI for invoking the same CLI executable. I have a lot of CLIs that I'd love to have exposed as web tools.

Example:
<h3>input</h3>
<pre>
import fire

def process_pictures(picture_folder_path, days_back=10, process_faces=False):
    print("Doing work...This is a log")
    print(f"{picture_folder_path=}, {days_back=}, {process_faces=}")

    for i in range(0, 10):
        print(f"Doing work...This is a log {i}")
        
    return True

if __name__ == "__main__":
    fire.Fire(process_pictures)
</pre>

which could quickly generate: (1) the UI, and (2) a backend to wire things up. Bonus credit for getting tables, image paths, and other complex UIs working.

<h3>output: a working Web App</h3>
<div class="example">
    <h1>{{ app_name }}</h1>
    <form action="/" method="POST">
        <table>
            <tr>
                <th>Picture Folder Path:</th>
                <td><input type="text" name="picture_folder_path"
                        value="{% if request_form and 'picture_folder_path' in request_form %}{{request_form['picture_folder_path'][0]}}{% endif %}" />
                </td>
            </tr>
            <tr>
                <th>Days Back:</th>
                <td><input type="text" name="days_back"
                        value="{% if request_form and 'days_back' in request_form %}{{request_form['days_back'][0]}}{% else %}10{% endif %}" />
                </td>
            </tr>
            <tr>
                <th>Process Faces:</th>
                <td>
                    <input type="radio" name="process_faces" value="true" />
                    <label for="process_faces_true">Yes</label>
                    <input type="radio" name="process_faces" value="false" checked="checked"/>
                    <label for="process_faces_false">No</label>
                </td>
            </tr>
            <tr>
                <td colspan="2">
                    <button>Submit</button>
                </td>
            </tr>
        </table>
        <h5>Result:</h5>
        <pre>{{ result }}</pre>
        <h5>Stdout (Print):</h5>
        <pre>{{ stdout }}</pre>
    </form>
</div>

The actual code as an example is below. I'm writing this as a test prompt for Codex. Then I'll do a bit of work to see if I can generate it.

<h3>output details</h3>
<ul>
<li><a href="https://raw.githubusercontent.com/xeb/cli2web/main/cli_process_pictures/templates/ui.html">ui.html</a></li>
<li><a href="https://github.com/xeb/cli2web/blob/main/cli_process_pictures/backend.py">backend.py</a></li>
</ul>

Maybe I can do this with <a href="https://openai.com/blog/openai-codex/">Codex</a>?

For now, the start of this endeavour is in GitHub at <a href="https://github.com/xeb/cli2web">xeb/cli2web</a>