---
title: type_info Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_info
helpviewer_keywords:
- class type_info
- type_info class
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
ms.openlocfilehash: 169a54373c66c2f6b33d71e68500c3bf85e871c3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560725"
---
# <a name="typeinfo-class"></a>type_info Sınıfı

**Type_info** sınıfı programında derleyici tarafından oluşturulan tür bilgilerini açıklar. Bu sınıfın nesneleri, tür için bir ada etkili şekilde bir işaretçi depolar. **Type_info** sınıfı ayrıca iki tür eşitlik için karşılaştırma veya harmanlama sırası için uygun kodlanmış bir değer depolar. Türler için kodlama kurallarını ve harmanlama sırası belirsizdir ve programdan programa farklılık gösterebilir.

`<typeinfo>` Üstbilgi dosyası kullanmak için dahil edilen olmalıdır **type_info** sınıfı. Arabirimin **type_info** sınıfı:

```cpp
class type_info {
public:
    virtual ~type_info();
    size_t hash_code() const
    _CRTIMP_PURE bool operator==(const type_info& rhs) const;
    _CRTIMP_PURE bool operator!=(const type_info& rhs) const;
    _CRTIMP_PURE int before(const type_info& rhs) const;
    _CRTIMP_PURE const char* name() const;
    _CRTIMP_PURE const char* raw_name() const;
};
```

Nesnelerin örneği oluşturulamıyor **type_info** sınıfı yalnızca bir özel kopya Oluşturucu olduğundan doğrudan sınıf. Bir (geçici) oluşturmak için tek yolu **type_info** kullanılacak nesnedir [TypeID](../cpp/typeid-operator.md) işleci. Atama işleci de özel olduğundan, kopyalayamaz veya sınıfın nesneleri Ata **type_info**.

`type_info::hash_code` türü değerleri için uygun bir karma işlevi tanımlar **typeinfo** dizin değerlerinin dağıtımına.

İşleçler `==` ve `!=` eşitlik ve eşitsizlik için diğer karşılaştırmak için kullanılan **type_info** nesneleri, sırasıyla.

Türlerin ve devralma ilişkilerinin harmanlama sırası arasında bir bağlantı yoktur. Kullanım `type_info::before` türlerin harmanlama sırasını belirlemek için üye işlevi. Garanti yoktur, `type_info::before` farklı programlar veya hatta farklı çalışmalarında aynı programın aynı sonucu verir. Bu şekilde `type_info::before` address-of benzer `(&)` işleci.

`type_info::name` Üye işlevinin döndürdüğü bir `const char*` insanlar tarafından okunabilen tür adını temsil eden boş sonlandırılmış bir dize. İşaret edilen bellek önbelleğe alınır ve hiçbir zaman doğrudan kaldırılmamalıdır.

`type_info::raw_name` Üye işlevinin döndürdüğü bir `const char*` nesne türünün düzenlenmiş adını temsil eden boş sonlandırılmış bir dize. Ad aslında yerden kazanmak için düzenlenmiş hâli içinde saklanır. Sonuç olarak, bu işlev hızlıdır, `type_info::name` , adın düzenlemesini kaldırması gerekmediğinden. Tarafından döndürülen dize `type_info::raw_name` işlevi karşılaştırma işlemlerinde yararlıdır, ancak okunabilir değil. Kullanıcı tarafından okunabilen bir dize ihtiyacınız varsa, `type_info::name` işlevini.

Tür bilgileri yalnızca şu durumlarda çok biçimli sınıflar için oluşturulan [/GR (çalışma zamanı türü bilgileri etkinleştir)](../build/reference/gr-enable-run-time-type-information.md) derleyici seçeneği belirtildi.

## <a name="see-also"></a>Ayrıca bkz.

[Çalışma Zamanı Tür Bilgileri](../cpp/run-time-type-information.md)