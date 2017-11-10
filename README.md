# Usage

```
import org.apache.spark._
import org.apache.spark.streaming._


// Host
// Port
// Keystore File Location
// Keystore Password
// SSL Version
def main(args: Array[String]) {
    val conf = new SparkConf()

    val ssc = new StreamingContext(conf, Seconds(30))
    val lines = ssc.receiverStream(
        new SSLSocketReceiver(
            "127.0.0.1",
            12345,
            "path_to_ssl_keystore",
            "keystore_password",
            "SSL_Version"
        )
    )
}