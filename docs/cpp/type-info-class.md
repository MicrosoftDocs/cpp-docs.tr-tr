---
description: 'Hakkında daha fazla bilgi edinin: type_info sınıfı'
title: type_info Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_info
helpviewer_keywords:
- class type_info
- type_info class
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
ms.openlocfilehash: 6be4d6774842ad015b34e771455026ca27e6539b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295321"
---
# <a name="type_info-class"></a>type_info Sınıfı

**Type_info** sınıfı, program içinde derleyici tarafından oluşturulan tür bilgilerini açıklar. Bu sınıfın nesneleri, tür için bir ada etkili şekilde bir işaretçi depolar. **Type_info** sınıfı, eşitlik veya harmanlama sırası için iki türü karşılaştırmak üzere uygun kodlanmış bir değeri de depolar. Türler için kodlama kurallarını ve harmanlama sırası belirsizdir ve programdan programa farklılık gösterebilir.

`<typeinfo>` **Type_info** sınıfını kullanabilmeniz için üst bilgi dosyası eklenmelidir. **Type_info** sınıfı için arabirim:

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

Sınıfın yalnızca bir özel kopya Oluşturucusu olduğundan, **type_info** sınıfının nesnelerini doğrudan örnekleyemezsiniz. Bir (geçici) **type_info** nesnesi oluşturmanın tek yolu [TypeId](../cpp/typeid-operator.md) işlecini kullanmaktır. Atama işleci de özel olduğundan, **type_info** sınıf nesnelerini kopyalayamaz veya atayamazsınız.

`type_info::hash_code`**TypeInfo** türündeki değerleri dizin değerlerinin dağıtımına eşlemek için uygun bir karma işlevi tanımlar.

İşleçler `==` ve `!=` diğer **type_info** nesneleriyle sırasıyla eşitlik ve eşitsizlik için karşılaştırma yapmak için kullanılabilir.

Türlerin ve devralma ilişkilerinin harmanlama sırası arasında bir bağlantı yoktur. `type_info::before`Türlerin harmanlama sırasını öğrenmek için üye işlevini kullanın. Aynı `type_info::before` sonucu farklı programlarla veya hatta aynı programın farklı çalışmalarından elde edecek bir garanti yoktur. Bu şekilde, `type_info::before` Adres `(&)` işlecine benzer.

`type_info::name`Üye işlevi, `const char*` türün okunabilir adını temsil eden null ile sonlandırılmış bir dizeye döndürür. İşaret edilen bellek önbelleğe alınır ve hiçbir zaman doğrudan kaldırılmamalıdır.

`type_info::raw_name`Üye işlevi, `const char*` nesne türünün düzenlenmiş adını temsil eden, null ile sonlandırılmış bir dizeye döndürür. Ad aslında yerden kazanmak için düzenlenmiş hâli içinde saklanır. Sonuç olarak, bu işlev `type_info::name` adı süslemek gerekmediğinden daha hızlıdır. İşlev tarafından döndürülen dize, `type_info::raw_name` karşılaştırma işlemlerinde faydalıdır ancak okunabilir değildir. İnsan tarafından okunabilen bir dizeye ihtiyacınız varsa, `type_info::name` bunun yerine işlevini kullanın.

Tür bilgileri, yalnızca [/gr (Run-Time türü bilgilerini etkinleştir)](../build/reference/gr-enable-run-time-type-information.md) derleyici seçeneği belirtilmişse polimorfik sınıflar için oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

[Çalışma Zamanı Türü Bilgileri](../cpp/run-time-type-information.md)
