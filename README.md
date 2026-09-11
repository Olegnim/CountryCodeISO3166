# Пример использования

## Преобразует числовой код валюты (ISO 4217) в буквенный код (ISO 3166-1: alpha-2)
```
let country = CountryCodeISO3166(rawValue: AppConfiguration.shared.tenant?.countryCode ?? 1)?.alpha2 ?? ""
// Вывод в формате: alpha2 = RU (пример)
print("alpha2 = \(country)")
```

## Вместе ищем друзей
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

## Берем название страны (для разных целей)
```
private func getCountryName() -> String? {
    guard let countryCode = SomeConfiguration.countryCode else { return nil }
    guard let iso = CountryCodeISO3166(rawValue: countryCode) else { return nil }
    return iso.name
}
```
