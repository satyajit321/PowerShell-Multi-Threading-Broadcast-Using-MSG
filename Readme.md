<div><strong>.Synopsis</strong><br /> &nbsp;Sends a message to all users in the specified serverlist parallelly\multi-threaded.</div>
<div>&nbsp;This script helps network administrators with Windows 7,8 clients and Windows 2008,2012 servers to use the MSG utility like the old "NET SEND" command.<br /> <strong>.DESCRIPTION</strong><br /> &nbsp;&nbsp; Calls each msg independent of the other msg.exe call irrespective of the completion state.<br /> &nbsp;&nbsp; The script can be easily modified to send it to specific users instead locally.</div>
<div><br /> <strong>.EXAMPLE</strong><br /> &nbsp;&nbsp; Msg-TSUsersMultiThreaded.ps1<br /> <strong>.EXAMPLE</strong><br /> Use notepad to list each server in a new line<br /> Serverlist.txt - Put it in the same location as the PS Script.<br /> Server1<br /> Server2<br /> Server3</div>
<div>Attached sample file: <a id="143093" href="/scriptcenter/site/view/file/143093/1/Serverlist.txt"> Serverlist.txt</a></div>
<div><strong>.EXAMPLE</strong><br /> Msg-TSUsersMultiThreaded.ps1<br /> #With KeepErrors = $True</div>
<div>------------------------<br /> Server: localhost1<br /> Error 1722 getting session names<br /> PS system32&gt;<br /> ------------------------</div>
<div><strong>.EXAMPLE</strong><br /> Msg-TSUsersMultiThreaded.ps1<br /> A common log is visible on the progress, but it doesn't state if the msg.exe call was success or failure</div>
<div>Executing: 'Server: localhost'<br /> &nbsp;msg.exe *&nbsp; /server:localhost 'Server will be down at 1PM today'<br /> Executing: 'Server: localhost1'<br /> &nbsp;msg.exe *&nbsp; /server:localhost1 'Server will be down at 1PM today'</div>
<div>&nbsp;</div>
<div>This is the essence of the script:</div>
<div>
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>PowerShell</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">powershell</span>
<pre class="hidden">msg "satyajit" `"Let`'s meet at 1PM today `"</pre>
<div class="preview">
<pre class="powershell">msg&nbsp;<span class="powerShell__string">"satyajit"</span>&nbsp;`<span class="powerShell__string">"Let`'s&nbsp;meet&nbsp;at&nbsp;1PM&nbsp;today&nbsp;`"</span></pre>
</div>
</div>
</div>
<div class="endscriptcode"></div>
<div class="endscriptcode">Sample Run:</div>
<div class="endscriptcode">&nbsp;
<div class="scriptcode">
<div class="pluginEditHolder" pluginCommand="mceScriptCode">
<div class="title"><span>PowerShell</span></div>
<div class="pluginLinkHolder"><span class="pluginEditHolderLink">Edit</span>|<span class="pluginRemoveHolderLink">Remove</span></div>
<span class="hidden">powershell</span>
<pre class="hidden">PS C:\Script&gt; C:\Script\Msg-TSUsersMultiThreaded.ps1
Executing: 'Server: Localhost'
 msg.exe *  /server:Localhost Server will be down at 1PM today`, please save your work and logoff before that.
Executing: 'Server: Server1'
 msg.exe *  /server:Server1 Server will be down at 1PM today`, please save your work and logoff before that.
Executing: 'Server: Server2'
 msg.exe *  /server:Server2 Server will be down at 1PM today`, please save your work and logoff before that.
Executing: 'Server: Server3'
 msg.exe *  /server:Server3 Server will be down at 1PM today`, please save your work and logoff before that.
Executing: 'Server: Localhost'
 msg.exe *  /server:Localhost Server will be down at 1PM today`, please save your work and logoff before that.
PS C:\Script&gt; </pre>
<div class="preview">
<pre class="powershell"><span class="powerShell__alias">PS</span>&nbsp;C:\Script&gt;&nbsp;C:\Script\Msg<span class="powerShell__operator">-</span>TSUsersMultiThreaded.ps1&nbsp;
Executing:&nbsp;<span class="powerShell__string">'Server:&nbsp;Localhost'</span>&nbsp;
&nbsp;msg.exe&nbsp;<span class="powerShell__operator">*</span>&nbsp;&nbsp;<span class="powerShell__operator">/</span>server:Localhost&nbsp;Server&nbsp;will&nbsp;be&nbsp;down&nbsp;at&nbsp;1PM&nbsp;today`,&nbsp;please&nbsp;save&nbsp;your&nbsp;work&nbsp;and&nbsp;logoff&nbsp;before&nbsp;that.&nbsp;
Executing:&nbsp;<span class="powerShell__string">'Server:&nbsp;Server1'</span>&nbsp;
&nbsp;msg.exe&nbsp;<span class="powerShell__operator">*</span>&nbsp;&nbsp;<span class="powerShell__operator">/</span>server:Server1&nbsp;Server&nbsp;will&nbsp;be&nbsp;down&nbsp;at&nbsp;1PM&nbsp;today`,&nbsp;please&nbsp;save&nbsp;your&nbsp;work&nbsp;and&nbsp;logoff&nbsp;before&nbsp;that.&nbsp;
Executing:&nbsp;<span class="powerShell__string">'Server:&nbsp;Server2'</span>&nbsp;
&nbsp;msg.exe&nbsp;<span class="powerShell__operator">*</span>&nbsp;&nbsp;<span class="powerShell__operator">/</span>server:Server2&nbsp;Server&nbsp;will&nbsp;be&nbsp;down&nbsp;at&nbsp;1PM&nbsp;today`,&nbsp;please&nbsp;save&nbsp;your&nbsp;work&nbsp;and&nbsp;logoff&nbsp;before&nbsp;that.&nbsp;
Executing:&nbsp;<span class="powerShell__string">'Server:&nbsp;Server3'</span>&nbsp;
&nbsp;msg.exe&nbsp;<span class="powerShell__operator">*</span>&nbsp;&nbsp;<span class="powerShell__operator">/</span>server:Server3&nbsp;Server&nbsp;will&nbsp;be&nbsp;down&nbsp;at&nbsp;1PM&nbsp;today`,&nbsp;please&nbsp;save&nbsp;your&nbsp;work&nbsp;and&nbsp;logoff&nbsp;before&nbsp;that.&nbsp;
Executing:&nbsp;<span class="powerShell__string">'Server:&nbsp;Localhost'</span>&nbsp;
&nbsp;msg.exe&nbsp;<span class="powerShell__operator">*</span>&nbsp;&nbsp;<span class="powerShell__operator">/</span>server:Localhost&nbsp;Server&nbsp;will&nbsp;be&nbsp;down&nbsp;at&nbsp;1PM&nbsp;today`,&nbsp;please&nbsp;save&nbsp;your&nbsp;work&nbsp;and&nbsp;logoff&nbsp;before&nbsp;that.&nbsp;
<span class="powerShell__alias">PS</span>&nbsp;C:\Script&gt;&nbsp;</pre>
</div>
</div>
</div>
<div class="endscriptcode">&nbsp;</div>
</div>
<div class="endscriptcode"><img id="143097" src="https://github.com/satyajit321/PowerShell-Multi-Threading-Broadcast-Using-MSG/blob/master/%5B143097%5D%20MsgPowerShell.png" alt="" width="434" height="333" /></div>
<div class="endscriptcode"></div>
<div class="endscriptcode"></div>
<div class="endscriptcode">Inputs and ideas from the excellent blog by Jose on <a href="http://blogs.technet.com/b/josebda/archive/2012/03/03/using-windows-powershell-to-run-old-command-line-tools-and-their-weirdest-parameters.aspx" target="_blank"> "Using Windows PowerShell to run old command line tools (and their weirdest parameters)"</a>.</div>
<div class="endscriptcode">&nbsp;</div>
<div class="endscriptcode">&nbsp;</div>
<div class="endscriptcode">&nbsp;</div>
<div class="endscriptcode"><strong>References:</strong></div>
<div class="endscriptcode">&nbsp;</div>
<div class="endscriptcode">Msg : Sends a message to a user.</div>
<div class="endscriptcode">&nbsp;</div>
<div class="endscriptcode"><a href="https://technet.microsoft.com/en-us/library/bb490796.aspx?f=255&amp;MSPPError=-2147217396">https://technet.microsoft.com/en-us/library/bb490796.aspx?f=255&amp;MSPPError=-2147217396</a></div>
<div class="endscriptcode">&nbsp;</div>
<div class="endscriptcode">&nbsp;</div>
<div class="endscriptcode">Using Windows PowerShell to run old command line tools (and their weirdest parameters)</div>
<div class="endscriptcode"><a href="http://blogs.technet.com/b/josebda/archive/2012/03/03/using-windows-powershell-to-run-old-command-line-tools-and-their-weirdest-parameters.aspx">http://blogs.technet.com/b/josebda/archive/2012/03/03/using-windows-powershell-to-run-old-command-line-tools-and-their-weirdest-parameters.aspx</a></div>
<div class="endscriptcode">&nbsp;</div>
</div>
