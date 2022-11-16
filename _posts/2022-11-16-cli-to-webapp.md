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
    print("Doing work...")

if __name__ == "__main__":
    fire.Fire(process_pictures)

</pre>

which could quickly generate: (1) the UI, and (2) a backend to wire things up. Bonus credit for getting tables, image paths, and other complex UIs working.

<h3>output UI</h3>
<div class="example">
<form>
    <table>
        <tr>
            <th>Picture Folder Path:</th>
            <td><input type="text" name="picture_folder_path" /></td>
        </tr>
        <tr>
            <th>Days Back:</th>
            <td><input type="text" name="days_back" value="10" /></td>
        </tr>
        <tr>
            <th>Process Faces:</th>
            <td>
                <input type="radio" name="process_faces_true" value="true" />
                <label for="process_faces_true">Yes</label>
                <input type="radio" name="process_faces_false" value="false" />
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
    <pre>Doing work...
    </pre>
</form>
</div>

The actual code as an example is below. I'm writing this as a test prompt for Codex. Then I'll do a bit of work to see if I can generate it. It's a little like <a href="https://github.com/charmbracelet/vhs">VHS</a>.

<h3>output code: ui.html</h3>
<div class="example">
<pre>
&lt;form&gt;
    &lt;table&gt;
        &lt;tr&gt;
            &lt;th&gt;Picture Folder Path:&lt;/th&gt;
            &lt;td&gt;&lt;input type="text" name="picture_folder_path" /&gt;&lt;/td&gt;
        &lt;/tr&gt;
        &lt;tr&gt;
            &lt;th&gt;Days Back:&lt;/th&gt;
            &lt;td&gt;&lt;input type="text" name="days_back" value="10" /&gt;&lt;/td&gt;
        &lt;/tr&gt;
        &lt;tr&gt;
            &lt;th&gt;Process Faces:&lt;/th&gt;
            &lt;td&gt;
                &lt;input type="radio" name="process_faces_true" value="true" /&gt;
                &lt;label for="process_faces_true"&gt;Yes&lt;/label&gt;
                &lt;input type="radio" name="process_faces_false" value="false" /&gt;
                &lt;label for="process_faces_false"&gt;No&lt;/label&gt;
            &lt;/td&gt;
        &lt;/tr&gt;
        &lt;tr&gt;
            &lt;td colspan="2"&gt;
                &lt;button&gt;Submit&lt;/button&gt;
            &lt;/td&gt;
        &lt;/tr&gt;
    &lt;/table&gt;
    &lt;h5&gt;Result:&lt;/h5&gt;
    &lt;pre&gt; { { result } } &lt;/pre&gt;
&lt;/form&gt;
</pre>
</div>

<h3>output code: backend.py</h3>
<div class="example">
<pre>
# will write this later...
</pre>
</div>

Maybe I can do this with <a href="https://openai.com/blog/openai-codex/">Codex</a>?