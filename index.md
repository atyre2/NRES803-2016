---
layout: workshop
root: .
venue: "University of Nebraska-Lincoln"      # brief name of host site without address (e.g., "Euphoric State University")
address: "3310 Holdrege Avenue, Lincoln, Nebraska"    # street address of workshop (e.g., "123 Forth Street, Blimingen, Euphoria")
country: "US"    # country (lowercase two-letter ISO code such as "fr" - see https://en.wikipedia.org/wiki/ISO_3166-1)
language: "en"   # language (lowercase two-letter ISO code such as "fr" - see https://en.wikipedia.org/wiki/ISO_639-1)
latlng: "40.828505,-96.671770"     # fractional latitude and longitude (e.g., "41.7901128,-87.6007318"; you can use http://www.latlong.net/)
humandate: "Fall semester, 2016"  # human-readable date (e.g., "Feb 17-18, 2020")
humantime: "MW 10am - 11am, Friday 2:00 pm - 4:50 pm"  # human-readable time (e.g., "9:00 am - 4:30 pm")
startdate: "2016-08-11"  # use YYYY-MM-DD format like "2015-01-01"
instructor: ["Drew Tyre"] # list of names like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: []    # list of names like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
contact: "atyre2@unl.edu"    # contact email address for workshop organizer, such as "grace@hopper.org"
---
<!--
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'tools/check' *before* committing to make sure that changes are good.
-->


<h2 id="general">General Information</h2>

<!--
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
-->
<p>
  This is a semester long course on Ecological Statistics at the University of Nebraska-Lincoln. Any Nebraska University 
  graduate student may enroll using NRES 898 Special Topics. The course 
  is fully on-line, with synchronous help sessions every Friday afternoon at 2:00 pm, as
  well as Monday and Wednesday mornings at 10am-11am.
  This hands-on course focuses on variations of the linear model and model selection. The 
  goal is to equip students with the basic methods to analyse ecological data.
</p>

<!--
  AUDIENCE

  Explain who your audience is.  (In particular, tell readers if the
  workshop is only open to people from a particular institution.
-->
<p id="who">
  <strong>Who:</strong>
  The course is aimed at graduate students from Nebraska University.
  You should have a basic working knowledge of the statistical programming language R.
  You should be comfortable with estimating a linear model with normally distributed data,
  interpreting the results, and carrying out hypothesis tests on the overall model and 
  individual coefficients.
</p>

<!--
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use http://itouchmap.com/latlong.html to find the lat/long of an
  address.
-->
{% if page.latlng %}
<p id="where">
  <strong>Where:</strong>
  My address is {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latlng}}">Google Maps</a>.
  Online help sessions will use <a href="https://connect.unl.edu/ecostat/">Adobe Connect</a>. 
</p>
{% endif %}

<!--
  SPECIAL REQUIREMENTS

  Modify the block below if there are any special requirements.
-->
<p id="requirements">
  <strong>Requirements:</strong> Participants must bring a laptop with
  a few specific software packages installed (listed
  <a href="#setup">below</a>). Participants should also have a USB headset with a microphone
  in order to participate in the online sessions effectively. The built-in 
  microphone on a laptop is <em>not</em> sufficient. Students are required to abide by the UNL
  student <a href="http://stuafs.unl.edu/dos/code">code of conduct</a>.
  Students are expected to adhere to guidelines concerning academic dishonesty 
  outlined in Section 4.2 of University's Student Code of Conduct. Students are 
  encouraged to contact the instructor for clarification of these guidelines if 
  they have questions or concerns. The SNR policy on Academic Dishonesty is available 
  <a href="http://snr.unl.edu/employeeinfo/information/employeehandbook-single.asp?infocode=S162">here</a>.<br>
  <strong>Students with disabilities:</strong>
  Students with disabilities are encouraged to contact the instructor for a 
  confidential discussion of their individual needs for academic accommodation. 
  It is the policy of the University of Nebraska-Lincoln to provide flexible and 
  individualized accommodation to students with documented disabilities that may 
  affect their ability to fully participate in course activities or to meet course 
  requirements. To receive accommodation services, students must be registered 
  with the Services for Students with Disabilities (SSD) office, 132 Canfield 
  Administration, 472-3787 voice or TTY.
</p>

<!--
  CONTACT EMAIL ADDRESS

  Display the contact email address set in the header.  If an address
  isn't set in the header, the Software Carpentry admin address is
  used.
-->
<p id="contact">
  <strong>Contact</strong>:
  Please mail
  {% if page.contact %}
    <a href='mailto:{{page.contact}}'>{{page.contact}}</a>
  {% else %}
    <a href='mailto:{{site.contact}}'>{{site.contact}}</a>
  {% endif %}
  for more information.
</p>

<!--<hr/>
<h2 id="assessment">Assessment</h2>
<p>
  The primary goal of this course is skill building, but it <em>is</em> a
  university course and I do need to give you a grade. Each week I will have 
  you turn in a text file containing your answers to a set of challenges. The challenges
  are listed at the end of each lesson page. Each assignment is due at <em>5pm on Friday of
  of the week it is assigned.</em> Late assignments will receive a score of zero unless
  prior approval is granted. Each challenge will be worth 5 points,
  and I will give partial grades where possible. For example, in the first week there
  are 2 lesson pages with 5 challenges each. Therefore week 1 will be worth a total 
  of 50 points. The total number of points over the entire semester will be approximately
  13 * 50 = 650. There will be no challenges the first week, during spring break or during dead week. 
  I may have to adjust this as we go forward, but in general assume that each week's
  work contributes equally to your overall grade. The final percentage score will be
  converted into letter grades as follows:<br>
  &gt;90% A, &gt;80% but &lt/90% B, &gt;70% but &lt;80% C,  &gt;60% but &lt;70% D, and
  &lt;60% F. <br>
  Note that I am not grading attendance at the synchronous sessions. You are 
  welcome to skip those or jump ahead as you wish. <br>
  <strong>NOTE: I may choose to "live code" some sessions</strong>, rather than provide
  video tutorials. These sessions will be recorded but the quality will not be as good.
  I am doing this because I want to learn the best way to present this material, and to
  do that I need to try some experiments. 
</p>
-->
<hr/>

<!--
  SCHEDULE

  Show the workshop's schedule.  Edit the items and times in the table
  to match your plans.  You may also want to change 'Day 1' and 'Day
  2' to be actual dates or days of the week.
-->
<h2 id="schedule">Schedule</h2>



<div class="row">
  <div class="col-md-6">
    <h3>Module 1</h3>
    <table class="table table-striped">
      <tr> <td>Week</td> <td>Topic</td> <td>Assignment Due</td></tr>
      <tr> <td>Week 1 -- Aug 22</td>  <td><a href='week1.html'>Introductions, setup, Review linear models I</a></td> <td></td></tr>
      <tr> <td>Week 2 -- Aug 29</td>  <td><a href='week2.html'>Review of linear models II</a> </td> <td></td> </tr>
      <tr> <td>Week 3 -- Sep 5</td>  <td><a href='week3.html'>Model Selection & Power</a> </td> <td>Linear Models</td></tr>
      <tr> <td>Week 4 -- Sep 12</td>  <td><a href='week4.html'>Model Selection AIC, BIC and friends</a></td><td>Preproposal</td></tr>
    </table>
  </div>
</div>
<div class="row">
  <div class="col-md-6">
    <h3>Module 2</h3>
    <table class="table table-striped">
      <tr> <td>Week</td> <td>Topic</td> <td>Assignment Due</td></tr>
      <tr> <td>5 -- Sep 19</td>  <td><a href='week5.html'>Generalized Linear Models</a></td><td>Nematodes</td> </tr>
      <tr> <td>6 -- Sep 26</td>  <td><a href='week6.html'>Generalized Additive Models</a></td><td>Mt Lofty Birds</td> </tr>
      <tr> <td>7 -- Oct 3</td>  <td><a href='week7.html'>What's the smoothest path?</a></td> <td>Preproposal Discussion</td></tr>
      <tr> <td>8 -- Oct 10</td>  <td><a href='week8.html'>Regression trees and forests</a></td><td></td> </tr>   
    </table>
  </div>
</div>

<div class="row">
  <div class="col-md-6">
    <h3>Module 3</h3>
    <table class="table table-striped">
      <tr> <td>Week</td> <td>Topic</td> <td>Assignment Due</td></tr>
      <tr> <td>9 -- Oct 17</td>  <td>FALL BREAK No Class</td><td></td> </tr>
      <tr> <td>10 -- Oct 24</td>  <td><a href='week10.html'>Mixing it up I</a></td> <td>What's the Best Shape</td></tr>
      <tr> <td>11 -- Oct 31</td>  <td><a href='week11.html'>Mixing it up II</a></td><td>Project Intro/methods</td> </tr>
      <tr> <td>12 -- Nov 7</td>  <td><a href='week12.html'>Choosing a mixed model</a></td><td></td> </tr>
    </table>
  </div>
</div>
<div class="row">
  <div class="col-md-6">
    <h3>Module 4</h3>
    <table class="table table-striped">
      <tr> <td>Week</td> <td>Topic</td> <td>Assignment Due</td></tr>
      <tr> <td>13 -- Nov 14</td>  <td><a href='week13.html'>Time to Event Data</a></td><td>Herbivore Shadows</td> </tr>
      <tr> <td>14 -- Nov 21</td>  <td><a href='week14.html'>THANKSGIVING BREAK</a></td> <td></td></tr>
      <tr> <td>15 -- Nov 28</td>  <td><a href='week15.html'>Multivariate I</a></td><td></td> </tr>
      <tr> <td>16 -- Dec 5</td>  <td><a href='week16.html'>Multivariate II</a></td> <td></td></tr>
    </table>
  </div>
</div>


<hr/>

<!--
  SYLLABUS

  Show what topics will be covered.

  I've removed this section from the main page, because I have a seperate page for each week.
-->

<!--
  SETUP

  Delete irrelevant sections from the setup instructions.  Each
  section is inside a 'div' without any classes to make the beginning
  and end easier to find.

  This is the other place where people frequently make mistakes, so
  please preview your site before committing, and make sure to run
  'tools/check' as well.
-->

<h2 id="setup">Setup</h2>

<p>
  To succeed in this course you will need
  access to the software described below. In addition, you will
  need an up-to-date web browser.
</p>
<p>
  We maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "https://github.com/swcarpentry/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>

<div id="shell"> <!-- Start of 'shell' section. -->
  <h3>The Bash Shell</h3>

  <p>
    Bash is a commonly-used shell that gives you the power to do simple
    tasks more quickly.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="shell-windows">Windows</h4>
      <ol>
        <li>Download the Git for Windows <a href="https://git-for-windows.github.io/">installer</a>.</li>
        <li>Run the installer and follow the steps bellow:
          <ol>
            <!-- Git 2.6.1 Setup -->
            <!-- Welcome to the Git Setup Wizard -->
            <li>Click on "Next".</li>
            <!-- Information -->
            <li>Click on "Next".</li>
            <!-- Select Destination Location -->
            <li>Click on "Next".</li>
            <!-- Select Components -->
            <li>Click on "Next".</li>
            <!-- Select Start Menu Folder -->
            <li>Click on "Next".</li>
            <!-- Adjusting your PATH environment -->
            <li>
              <strong>
                Select "Use Git from the Windows Command Prompt" and click on "Next".
              </strong>
                If you forgot to do this programs that you need for the workshop will not work properly.
                If this happens rerun the installer and select the appropriate option.
            </li>
            <!-- Configuring the line ending conversions -->
            <li>
              Click on "Next".
              <strong>
                Keep "Checkout Windows-style, commit Unix-style line endings" selected.
              </strong>
            </li>
            <!-- Configuring the terminal emulator to use with Git Bash -->
            <li>
              <strong>
                Select "Use Windows' default console window" and click on "Next".
              </strong>
            </li>
            <!-- Configuring experimental performance tweaks -->
            <li>Click on "Next".</li>
            <!-- Installing -->
            <!-- Completing the Git Setup Wizard -->
            <li>Click on "Finish".</li>
          </ol>
        </li>
      </ol>
      <p>This will provide you with both Git and Bash in the Git Bash program.</p>
    </div>
    <div class="col-md-4">
      <h4 id="shell-macosx">Mac OS X</h4>
      <p>
        The default shell in all versions of Mac OS X is Bash, so no
        need to install anything.  You access Bash from the Terminal
        (found in
        <code>/Applications/Utilities</code>). You may want to keep
        Terminal in your dock for this workshop.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="shell-linux">Linux</h4>
      <p>
        The default shell is usually Bash, but if your
        machine is set up differently you can run it by opening a
        terminal and typing <code>bash</code>.  There is no need to
        install anything.
      </p>
    </div>
  </div>
</div> <!-- End of 'shell' section. -->

<div id='git'> <!-- Start of 'Git' section. GitHub browser compatability
           is given at https://help.github.com/articles/supported-browsers/-->
  <h3>Git</h3>

  <p>
    Git is a version control system that lets you track who made changes
    to what when and has options for easily updating a shared or public
    version of your code
    on <a href="https://github.com/">github.com</a>. You will need a
    <a href="https://help.github.com/articles/supported-browsers/">supported</a>
    web browser (current versions of Chrome, Firefox or Safari,
    or Internet Explorer version 9 or above).
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="git-windows">Windows</h4>
      <p>
        Git should be installed on your computer as part of your Bash
        install (described above).
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="git-macosx">Mac OS X</h4>
      <p>
        <strong>For OS X 10.9 and higher</strong>, install Git for Mac
        by downloading and running the most recent "mavericks" installer from
        <a href="http://sourceforge.net/projects/git-osx-installer/files/">this list</a>.
        After installing Git, there will not be anything in your <code>/Applications</code> folder,
        as Git is a command line program.
        <strong>For older versions of OS X (10.5-10.8)</strong> use the
        most recent available installer labelled "snow-leopard"
        <a href="http://sourceforge.net/projects/git-osx-installer/files/">available here</a>.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="git-linux">Linux</h4>
      <p>
        If Git is not already available on your machine you can try to
        install it via your distro's package manager. For Debian/Ubuntu run
        <code>sudo apt-get install git</code> and for Fedora run
        <code>sudo yum install git</code>.
      </p>
    </div>
  </div>
</div> <!-- End of 'Git' section. -->

<div id="editor"> <!-- Start of 'editor' section. -->
  <h3>Text Editor</h3>

  <p>
    When you're writing code, it's nice to have a text editor that is
    optimized for writing code, with features like automatic
    color-coding of key words.  The default text editor on Mac OS X and
    Linux is usually set to Vim, which is not famous for being
    intuitive.  if you accidentally find yourself stuck in it, try
    typing the escape key, followed by <code>:q!</code> (colon, lower-case 'q',
    exclamation mark), then hitting Return to return to the shell.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="editor-windows">Windows</h4>
      <p>
        nano is a basic editor and the default that instructors use in the workshop.
        To install it,
        download the <a href="{{site.swc_installer}}">Software Carpentry Windows installer</a>
        and double click on the file to run it.
        <strong>This installer requires an active internet connection.</strong>
      </p>
      <p>
        Others editors that you can use are
        <a href="http://notepad-plus-plus.org/">Notepad++</a> or
        <a href="http://www.sublimetext.com/">Sublime Text</a>.
        <strong>Be aware that you must
          add its installation directory to your system path.</strong>
        Please ask your instructor to help you do this.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="editor-macosx">Mac OS X</h4>
      <p>
        nano is a basic editor and the default that instructors use in the workshop.
        It should be pre-installed.
      </p>
      <p>
        Others editors that you can use are
        <a href="http://www.barebones.com/products/textwrangler/">Text Wrangler</a> or
        <a href="http://www.sublimetext.com/">Sublime Text</a>.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="editor-linux">Linux</h4>
      <p>
        nano is a basic editor and the default that instructors use in the workshop.
        It should be pre-installed.
      </p>
      <p>
        Others editors that you can use are
        <a href="https://wiki.gnome.org/Apps/Gedit">Gedit</a>,
        <a href="http://kate-editor.org/">Kate</a> or
        <a href="http://www.sublimetext.com/">Sublime Text</a>.
      </p>
    </div>
  </div>
</div> <!-- End of 'editor' section. -->

<div id="r"> <!-- Start of 'R' section. -->
  <h3>R</h3>

  <p>
    <a href="http://www.r-project.org">R</a> is a programming language
    that is especially powerful for data exploration, visualization, and
    statistical analysis. To interact with R, we use
    <a href="http://www.rstudio.com/">RStudio</a>.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="r-windows">Windows</h4>
      <p>
        Install R by downloading and running
        <a href="http://cran.r-project.org/bin/windows/base/release.htm">this .exe file</a>
        from <a href="http://cran.r-project.org/index.html">CRAN</a>.
        Also, please install the
        <a href="http://www.rstudio.com/ide/download/desktop">RStudio IDE</a>.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="r-macosx">Mac OS X</h4>
      <p>
        Install R by downloading and running
        <a href="http://cran.r-project.org/bin/macosx/R-latest.pkg">this .pkg file</a>
        from <a href="http://cran.r-project.org/index.html">CRAN</a>.
        Also, please install the
        <a href="http://www.rstudio.com/ide/download/desktop">RStudio IDE</a>.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="r-linux">Linux</h4>
      <p>
        You can download the binary files for your distribution
        from <a href="http://cran.r-project.org/index.html">CRAN</a>. Or
        you can use your package manager (e.g. for Debian/Ubuntu
        run <code>sudo apt-get install r-base</code> and for Fedora run
        <code>sudo yum install R</code>).  Also, please install the
        <a href="http://www.rstudio.com/ide/download/desktop">RStudio IDE</a>.
      </p>
    </div>
  </div>
</div> <!-- End of 'R' section. -->

<div id="sql"> <!-- Start of 'SQLite' section. -->
  <h3>SQLite</h3>

  <p>
    SQL is a specialized programming language used with databases.  We
    use a simple database manager called
    <a href="http://www.sqlite.org/">SQLite</a> in our lessons.
  </p>

  <div class="row">
    <div class="col-md-4">
      <h4 id="sql-windows">Windows</h4>
      <p>
        The <a href="{{site.swc_installer}}">Software Carpentry Windows installer</a>
        installs SQLite for Windows.
        If you used the installer to configure nano, you don't need to run it again.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="sql-macosx">Mac OS X</h4>
      <p>
        SQLite comes pre-installed on Mac OS X.
      </p>
    </div>
    <div class="col-md-4">
      <h4 id="sql-linux">Linux</h4>
      <p>
        SQLite comes pre-installed on Linux.
      </p>
    </div>
  </div>

  <p><strong>If you installed Anaconda, it also has a copy of SQLite
    <a href="https://github.com/ContinuumIO/anaconda-issues/issues/307">without support to <code>readline</code></a>.
    Instructors will provide a workaround for it if needed.</strong></p>
</div> <!-- End of 'SQLite' section. -->

<!--
  Uncomment this section if you are using our virtual machine.

<div id="vm">
  <h3>Virtual Machine</h3>

  <p>
    Some instructors prefer to have learners use a virtual machine (VM)
    rather than install software on their own computers.  If your
    instructors have chosen to do this, please:
  </p>
  <ol>
    <li>
      Install <a href="https://www.virtualbox.org/">VirtualBox</a>.
    </li>
    <li>
      Download our <a href="{{site.swc_vm}}">VM image</a>.
      <strong>Warning:</strong> this file is 1.7 GByte, so please
      download it <em>before</em> coming to your workshop.
    </li>
    <li>
      Load the VM into VirtualBox by selecting "Import Appliance" and
      loading the <code>.ova</code> file.
    </li>
  </ol>
</div>
-->
