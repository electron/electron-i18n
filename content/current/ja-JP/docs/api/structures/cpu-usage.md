# CPUUsage オブジェクト

* `percentCPUUsage` Number - 最後の getCPUUsage 呼び出し以降に使用されたCPUの割合。 最初の呼び出しは 0 を返します。
* `idleWakeupsPerSecond` Number - The number of average idle CPU wakeups per second since the last call to getCPUUsage. 最初の呼び出しは 0 を返します。 Windows の場合は常に 0 を返します。
