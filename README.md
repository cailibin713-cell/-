# -
强制推荐：【⚡ 赛 马 娘 ⚡-哔哩哔哩】 https://b23.tv/pTaI7dy
【【蔡徐坤】小蔡家的鸡女仆-哔哩哔哩】 https://b23.tv/gNpHGZ7
【鸡哥大闹天宫-哔哩哔哩】 https://b23.tv/4lb95Oq
【俺の愛kunが!!!-哔哩哔哩】 https://b23.tv/qiXxh1y
鸡你太美小游戏
Dim g, vz, xt, yt As Single

Dim vt, vl, a As Single

Dim fen As Integer

Private Sub Form_Load()

L2.Caption = "计分："

L3.Caption = "0"

fen = 0

T1.Interval = HS1.SmallChange

T1.Enabled = False

vz = 200

End Sub

Private Sub Form_Click()

T1.Interval = HS1.Value

T1.Enabled = True

End Sub

Private Sub Form_MouseDown(Button As Integer, Shift As Integer, X As Single, Y As Single)

I3.Top = 9000

I3.Left = 6000

g = 0

xt = X - I3.Left

yt = Y - I3.Top

If a < 0 Then

a = -a

End If

a = xt / yt

If yt > 0 Then

vl = -a * vz / ((a ^ 2 + 1) ^ 0.5)

vt = -vz / ((a ^ 2 + 1) ^ 0.5)

Else

vl = a * vz / ((a ^ 2 + 1) ^ 0.5)

vt = vz / ((a ^ 2 + 1) ^ 0.5)

End If

g = g - vt

End Sub



Private Sub T1_Timer()

If I3.Top < 15000 Then

g = g + 2

I3.Top = I3.Top + g

I3.Left = I3.Left - vl

If ((L1.Top < I3.Height + I3.Top) And (L1.Top > I3.Top)) And ((I3.Left + I3.Width > L1.Left) And (L1.Left + L1.Width > I3.Left + I3.Width)) Then

L1.Left = Int(Rnd * 6000) + 10000

L1.Top = Int(Rnd * 4000) + 5000

fen = fen + 1

L3.Caption = fen

End If

End If

End Sub
