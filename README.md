# Minecraft-WindowsLog
How to patch WindowsLog on processhacker(and more)

```
import java.util.ArrayList;

import com.sun.jna.platform.win32.User32; 
import com.sun.jna.platform.win32.WinDef.HWND;

import gg.natsumi.k3ri.module.Module;

import com.sun.jna.platform.win32.WinUser; 

public class Sf {
	
	ArrayList<HWND> WindowLog = new ArrayList<HWND>();
	
	public Sf() {
		for(HWND w : WindowLog) {
			User32.INSTANCE.PostMessage(w, WinUser.WM_QUIT, null, null);
		}
	}
	
	public void InitWindowLog() {
		//First args argument = Window Class
		//Second args argument = Window Title
		WindowLog.add(User32.INSTANCE.FindWindow ("D3DFocusWindow", null));
		WindowLog.add(User32.INSTANCE.FindWindow ("SunAwtToolkit", null));
		WindowLog.add(User32.INSTANCE.FindWindow ("IME", null));
		WindowLog.add(User32.INSTANCE.FindWindow ("SunAwtFrame", null));
		WindowLog.add(User32.INSTANCE.FindWindow ("MSCTFIME UI", null));
	}

}
```
