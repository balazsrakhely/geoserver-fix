# Adjust Geoserver code to accept LocalDateTime

Based on the stacktrace, the error is in geoserver/src/wfs/src/main/java/org/geoserver/wfs/json/GeoJSONGetFeatureResponse.java line 458
Injected code:
```java
// Converting received LocalDateTime object to Date
if (value instanceof LocalDateTime) {
    value = Date.from(((LocalDateTime) value).atZone(ZoneId.systemDefault()).toInstant());
}
```