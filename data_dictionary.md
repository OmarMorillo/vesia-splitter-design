# Data dictionary

Every column used in `notebooks/vesia_splitter.ipynb`. Source: Baseball Savant (MLB Advanced Media), 2026 regular season.

| Column | File | Meaning | Units |
|---|---|---|---|
| pitch_name | pitch files | Pitch type assigned by Statcast | text |
| game_date | pitch files | Date of the game | YYYY-MM-DD |
| p_throws | pitch files | Pitcher's throwing hand (L or R) | text |
| stand | pitch files | Batter's side (L or R) | text |
| description | pitch files | Result of the pitch (ball, called strike, swinging strike, foul, in play…) | text |
| events | pitch files | Result of the plate appearance, on its last pitch | text |
| release_speed | pitch files | Velocity out of the hand | mph |
| release_spin_rate | pitch files | Total spin rate out of the hand | rpm |
| spin_axis | pitch files | Spin direction; 180° = pure backspin (12:00), every 30° = one clock hour | degrees |
| pfx_x | pitch files | Horizontal movement vs a spinless ball, from the catcher's view | feet |
| pfx_z | pitch files | Vertical movement vs a spinless ball (induced vertical break) | feet |
| arm_angle | pitch files | Arm slot at release | degrees |
| release_pos_x / release_pos_z | pitch files | Release side (catcher's view) and release height | feet |
| release_extension | pitch files | Distance in front of the rubber at release | feet |
| vx0, vy0, vz0, ax, ay, az | pitch files | Ball velocity and acceleration at release, used for VAA | ft/s, ft/s² |
| estimated_woba_using_speedangle | pitch files | Expected wOBA of the plate appearance ending on this pitch | rate |
| **ivb** | created | Induced vertical break: pfx_z × 12 | inches |
| **hb_arm** | created | Horizontal break toward the pitcher's arm side: pfx_x × 12, sign flipped for right-handers | inches |
| **hb_pitcher_view** | created | Horizontal break from behind the pitcher: −pfx_x × 12 | inches |
| **vaa** | created | Vertical approach angle at the front of home plate | degrees |
| **whiff / swing** | created | True if the pitch was a swing and miss / any swing | True/False |
| ff_avg_speed, ch_avg_speed, sl_avg_speed, fs_avg_speed | lb_pitch_arsenals | Season average velocity by pitch type | mph |
| active_spin_* | lb_active_spin | Share of spin that creates movement (spin efficiency) | % |
| ball_angle | lb_arm_angles | Season arm angle | degrees |
| pitches, velocity, spin_rate, api_break_z_induced, api_break_x_arm, arm_angle, swing_miss_percent, xwoba | lb_splitters | Each pitcher's splitter averages and results (movement in feet, arm side positive) | mixed |
| **velo_gap** | created | Splitter velocity minus the pitcher's four-seamer velocity | mph |
