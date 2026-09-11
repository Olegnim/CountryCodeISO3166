# Пример использования
```
if let alpha2Code = CountryCodeISO3166.numericToAlpha2(numericCode: 032) {
    print("Alpha-2 code for 032: \(alpha2Code)") // AR is expected
} else {
    print("Code not found.")
}
```

```
private func getCountryName() -> String? {
    guard let countryCode = SomeConfiguration.countryCode else { return nil }
    guard let iso = CountryCodeISO3166(rawValue: countryCode) else { return nil }
    return iso.name
}
```
