---
title: type_info Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_info
helpviewer_keywords:
- class type_info
- type_info class
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
ms.openlocfilehash: 7a016fe8fee4e5765e6172184bfa9c90eecbc687
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160677"
---
# <a name="type_info-class"></a>type_info Sınıfı

**Type_info** sınıfı, program içinde derleyici tarafından oluşturulan tür bilgilerini açıklar. Bu sınıfın nesneleri, tür için bir ada etkili şekilde bir işaretçi depolar. **Type_info** sınıfı, eşitlik veya harmanlama sırası için iki türü karşılaştırmak üzere uygun kodlanmış bir değeri de depolar. Türler için kodlama kurallarını ve harmanlama sırası belirsizdir ve programdan programa farklılık gösterebilir.

**Type_info** sınıfının kullanılabilmesi için `<typeinfo>` üst bilgi dosyası eklenmelidir. **Type_info** sınıfı için arabirim:

```cpp
class type_info {
public:
    type_info(const type_info& rhs) = delete; // cannot be copied
    virtual ~type_info();
    size_t hash_code() const;
    _CRTIMP_PURE bool operator==(const type_info& rhs) const;
    type_info& operator=(const type_info& rhs) = delete; // cannot be copied
    _CRTIMP_PURE bool operator!=(const type_info& rhs) const;
    _CRTIMP_PURE int before(const type_info& rhs) const;
    size_t hash_code() const noexcept;
    _CRTIMP_PURE const char* name() const;
    _CRTIMP_PURE const char* raw_name() const;
};
```

Sınıfın yalnızca bir özel kopya Oluşturucusu olduğundan, **type_info** sınıfının nesnelerini doğrudan örnekleyemezsiniz. Bir (geçici) **type_info** nesnesi oluşturmanın tek yolu [TypeId](../cpp/typeid-operator.md) işlecini kullanmaktır. Atama işleci de özel olduğundan, **type_info**sınıf nesnelerini kopyalayamaz veya atayamazsınız.

`type_info::hash_code` **TypeInfo** türündeki değerleri dizin değerlerinin dağıtımına eşlemek için uygun bir karma işlevi tanımlar.

İşleçler `==` ve `!=`, sırasıyla diğer **type_info** nesneleriyle eşitlik ve eşitsizlik için karşılaştırmak üzere kullanılabilir.

Türlerin ve devralma ilişkilerinin harmanlama sırası arasında bir bağlantı yoktur. Türlerin harmanlama sırasını öğrenmek için `type_info::before` member işlevini kullanın. `type_info::before` aynı sonucu farklı programlarla veya hatta aynı programın farklı çalışmalarından işleyeceğimizi garanti etmez. Bu şekilde, `type_info::before` `(&)` işlecine benzer.

`type_info::name` member işlevi, türün okunabilir adını temsil eden null ile sonlandırılmış bir dizeye `const char*` döndürür. İşaret edilen bellek önbelleğe alınır ve hiçbir zaman doğrudan kaldırılmamalıdır.

`type_info::raw_name` member işlevi, nesne türünün düzenlenmiş adını temsil eden, null ile sonlandırılmış bir dizeye `const char*` döndürür. Ad aslında yerden kazanmak için düzenlenmiş hâli içinde saklanır. Sonuç olarak, adın süslemek gerekmediğinden, bu işlev `type_info::name` daha hızlıdır. `type_info::raw_name` işlevi tarafından döndürülen dize, karşılaştırma işlemlerinde faydalıdır ancak okunabilir değildir. İnsan tarafından okunabilen bir dizeye ihtiyacınız varsa, bunun yerine `type_info::name` işlevini kullanın.

Tür bilgileri, yalnızca [/gr (çalışma zamanı türü bilgilerini etkinleştir)](../build/reference/gr-enable-run-time-type-information.md) derleyici seçeneği belirtilmişse polimorfik sınıflar için oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

[Çalışma Zamanı Tür Bilgileri](../cpp/run-time-type-information.md)
