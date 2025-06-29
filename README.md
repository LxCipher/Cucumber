import org.openqa.selenium.edge.EdgeDriver;
import org.openqa.selenium.edge.EdgeOptions;

import java.util.HashMap;
import java.util.Map;

public class MobileEdgeEmulation {

    public static void main(String[] args) {
        // Mobile emulation config
        Map<String, Object> deviceMetrics = new HashMap<>();
        deviceMetrics.put("width", 412);
        deviceMetrics.put("height", 915);
        deviceMetrics.put("pixelRatio", 2.625);

        Map<String, Object> mobileEmulation = new HashMap<>();
        mobileEmulation.put("deviceMetrics", deviceMetrics);
        mobileEmulation.put("userAgent", "Mozilla/5.0 (Linux; Android 13; Pixel 7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/114.0.0.0 Mobile Safari/537.36");

        EdgeOptions options = new EdgeOptions();
        options.setExperimentalOption("mobileEmulation", mobileEmulation);
        options.setExperimentalOption("excludeSwitches", java.util.Arrays.asList("enable-automation"));
        options.setExperimentalOption("useAutomationExtension", false);

        EdgeDriver driver = new EdgeDriver(options);
        driver.get("https://www.whatismybrowser.com/");
    }
}
