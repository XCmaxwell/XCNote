### AVAudioSession 功能

```C
1.设置自己的App和其他的App音频是否同时存在， 或者中断其他app的音频。
2.手机静音模式下,自己App的音频是否播放出声音。
3.电话或者其他App中断自己App的音频，如何处理。
4.指定音频输入和输出的设备(比如输出声音的设备是用听筒，还是扬声器)。
5.是否支持录音和音频播放同时进行。
```



### AVAudioSessionCategory

| category                            | 录音 | 播放 | 是否允许混音 | 是否会被静音键/锁屏建 静音 | 作用场景 |
| ----------------------------------- | ---- | ---- | ------------ | -------------------------- | -------- |
| AVAudioSessionCategoryAmbient       |      |      |              |                            |          |
| AVAudioSessionCategorySoloAmbient   |      |      |              |                            |          |
| AVAudioSessionCategoryPlayback      |      |      |              |                            |          |
| AVAudioSessionCategoryRecord        |      |      |              |                            |          |
| AVAudioSessionCategoryPlayAndRecord |      |      |              |                            |          |
| AVAudioSessionCategoryMultiRoute    |      |      |              |                            |          |



### AVAudioSessionCategoryOption 

* 用于微调Category行为

| **CategoryOption**                   | **兼容的Category** | **功能**                 |
| ------------------------------------ | ------------------ | ------------------------ |
| MixWithOthers                        |                    | 支持和其他APP混音        |
| DuckOthers                           |                    | 系统智能调低其他APP音量  |
| AllowBluetooth                       |                    | 支持蓝牙音频输入         |
| DefaultToSpeaker                     |                    | 设置默认输出音频到扬声器 |
| InterruptSpokenAudioAndMixWithOthers |                    |                          |
| AllowBluetoothA2DP                   |                    | 允许蓝牙A2DP设备         |
| AllowAirPlay                         |                    | 允许AirPlay              |
| nOverrideMutedMicrophoneInterruption |                    |                          |



### AVAudioSessionMode

* 可以通过mode来定制Category的行为

| AVAudioSessionMode               |      |      |
| -------------------------------- | ---- | ---- |
| AVAudioSessionModeDefault        |      |      |
| AVAudioSessionModeVoiceChat      |      |      |
| AVAudioSessionModeVideoRecording |      |      |
| AVAudioSessionModeMeasurement    |      |      |
| AVAudioSessionModeMoviePlayback  |      |      |
| AVAudioSessionModeVideoChat      |      |      |
| AVAudioSessionModeSpokenAudio    |      |      |



### AVAudioSessionRouteSharingPolicy

| Policy                                        | 作用                                                         | 应用场景 |
| --------------------------------------------- | ------------------------------------------------------------ | -------- |
| AVAudioSessionRouteSharingPolicyDefault       | 路由音频输出常规规则                                         |          |
| AVAudioSessionRouteSharingPolicyLongFormAudio | 将输出路由到共享的长格式音频输出                             |          |
| AVAudioSessionRouteSharingPolicyLongForm      | 同上                                                         |          |
| AVAudioSessionRouteSharingPolicyIndependent   | 在iOS上，此值将设置为在路由选择器UI用于将视频定向到无线路由的情况下的系统 |          |
| AVAudioSessionRouteSharingPolicyLongFormVideo | 将输出路由到共享的长格式视频输出 <br/>(需要在info.plist添加"AVInitialRouteSharingPolicy") |          |



### 系统中断音频处理

* 一般性中断，例：电话、闹铃、日程提醒中断

  AVAudioSessionInterruptionNotification

* 线路改变， 例：耳机的插入/拔出、断开麦克风等
  AVAudioSessionRouteChangeNotification

* 被其他APP中断：

  AVAudioSessionSilenceSecondaryAudioHintNotification





