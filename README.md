<div align="center">

## Idle Auto away


</div>

### Description

this code show how to make an Auto Away like ICQ with Windows Api call GetLastInputInfo. Only work on Nt, 2000, and Xp not on 98,me...
 
### More Info
 
The value return to dwtime is the last time when the user move the mouse or use the keyboard. The time begin when the session is open.

Put a Timer and a textbox on a form. Name the textbox text1 and timer timer1 and copy and past this code.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Frédéric Thibault](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/fr-d-ric-thibault.md)
**Level**          |Intermediate
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |VB 6\.0
**Category**       |[Windows API Call/ Explanation](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/windows-api-call-explanation__1-39.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/fr-d-ric-thibault-idle-auto-away__1-28408/archive/master.zip)





### Source Code

```
Private Type tagLASTINPUTINFO
  cbSize As Long
  dwTime As Long
End Type
Private Declare Function GetLastInputInfo Lib "user32" (ByRef LASTINPUTINFO As tagLASTINPUTINFO) As Long
Private Sub Timer1_Timer()
  Dim mLast As tagLASTINPUTINFO
  mLast.cbSize = Len(mLast)
  Call GetLastInputInfo(mLast)
  Me.Text1.Text = mLast.dwTime
End Sub
```

