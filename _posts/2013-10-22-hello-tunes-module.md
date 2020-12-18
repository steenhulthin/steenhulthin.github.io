<p><a href="https://steen.hulthin.dk/blog/hello-led-strip-gadgeteer-module">Recently I had a look at the gadgeteer LED strip module</a>. This post is about the gadgeteer <a href="https://www.ghielectronics.com/catalog/product/434">Tunes module</a>. The tunes module is a rather crude sound generator. It can generate one track only and there is no control of the wave shape, but it is still good enough simple melodies or - better - an alarm sound.</p>

<h2>The Code</h2>

<pre><code>public partial class Program
{
    // This method is run when the mainboard is powered up or reset.   
    void ProgramStarted()
    {
        // Use Debug.Print to show messages in Visual Studio's "Output" window during debugging.
        Debug.Print("Program Started");
        tunes.AddNote(new Tunes.MusicNote(new Tunes.Tone(440), 500 ));
        tunes.AddNote(new Tunes.MusicNote(Tunes.Tone.C4, 500));
        tunes.AddNote(new Tunes.MusicNote(Tunes.Tone.D4, 500));
        tunes.AddNote(new Tunes.MusicNote(Tunes.Tone.E4, 500));
        tunes.AddNote(new Tunes.MusicNote(Tunes.Tone.F4, 500));
        tunes.AddNote(new Tunes.MusicNote(Tunes.Tone.G4, 500));
        tunes.AddNote(new Tunes.MusicNote(Tunes.Tone.A4, 500));
        tunes.AddNote(new Tunes.MusicNote(Tunes.Tone.B4, 500));
        tunes.AddNote(new Tunes.MusicNote(Tunes.Tone.C5, 500));
        tunes.Play();
    }
}
</code></pre>

<p>The tunes module is used but adding notes (<code>MusicNote</code>'s) to a queue - let's call it a melody - and then playing the melody with <code>Tunes.Play()</code>. It is also possible to stop the melody from playing further with <code>Tunes.Stop()</code>.</p>

<p>The <code>MusicNote</code> takes a <code>Tone</code> and a duration argument. It is very not clear from the documentation, but the duration is given in milliseconds.</p>

<p>The full solution is as usual on <a href="https://github.com/steenhulthin/HelloTuneModule">my github</a> page.</p>

<h2>The Result</h2>

<p>The result is a 440 Hz tone (same as A4 actually) and followed by a C major scale.</p>

<p>This is a video where you can hear what is sound like:</p>

<iframe width="420" height="315" src="//www.youtube.com/embed/WX2PESoJMvE" frameborder="0" allowfullscreen></iframe>
