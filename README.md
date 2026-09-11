# Пример использования

```
let country = CountryCodeISO3166(rawValue: AppConfiguration.shared.tenant?.countryCode ?? 1)?.alpha2 ?? ""
// Вывод в формате: alpha2 = RU (пример)
print("alpha2 = \(country)")
```

```
private var friendlyCountry: Bool {
    if let code = CountryCodeISO3166(rawValue: someCountryCode) {
        switch code {
        case .russia, .belarus, .kazakhstan, .china:
            return true
        default:
            return false
        }
    }
    return false
}
```

```
private func getCountryName() -> String? {
    guard let countryCode = SomeConfiguration.countryCode else { return nil }
    guard let iso = CountryCodeISO3166(rawValue: countryCode) else { return nil }
    return iso.name
}
```
