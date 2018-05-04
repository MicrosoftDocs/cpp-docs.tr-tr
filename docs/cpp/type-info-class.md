---
title: type_info sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- type_info
dev_langs:
- C++
helpviewer_keywords:
- class type_info
- type_info class
ms.assetid: 894ddda2-7de4-4da3-9404-d2c74e356c16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3e3138c9028f72327c9d4bf2c2f2e82c942dbde
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="typeinfo-class"></a>type_info Sınıfı
**Type_info** sınıfı programında derleyici tarafından üretilen türü bilgileri açıklar. Bu sınıfın nesneleri, tür için bir ada etkili şekilde bir işaretçi depolar. **Type_info** sınıfı, iki tür eşitlik için karşılaştırılması veya harmanlama sırası için uygun kodlanmış bir değer de depolar. Türler için kodlama kurallarını ve harmanlama sırası belirsizdir ve programdan programa farklılık gösterebilir.  
  
 `<typeinfo>` Üstbilgi dosyası içerilmelidir kullanmak için **type_info** sınıfı. Arabirim için **type_info** sınıfı:  
  
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
  
 Nesnelerin örneği oluşturulamıyor **type_info** sınıfı yalnızca özel kopya Oluşturucu olduğundan doğrudan sınıfı. (Geçici) oluşturmak için tek yolu **type_info** nesnesi kullanmaktır [TypeID](../cpp/typeid-operator.md) işleci. Atama işleci ayrıca özel olduğundan kopyalayamaz veya sınıfın nesnelerini atamak **type_info**.  
  
 **type_info::hash_code** türü değerleri eşlemek için uygun bir karma işlevi tanımlar **TypeInfo** dizin değerlerin bir dağıtım.  
  
 İşleçler `==` ve `!=` eşitlik ve eşitsizlik için diğer ile karşılaştırmak için kullanılan **type_info** nesneleri, sırasıyla.  
  
 Türlerin ve devralma ilişkilerinin harmanlama sırası arasında bir bağlantı yoktur. Kullanım **type_info::before** türleri harmanlama sırasını belirlemek için üye işlevi. Garantisi yoktur, **type_info::before** farklı programlar ya da aynı şekilde programın bile farklı çalıştırmalarını aynı sonucu verecek olan. Bu şekilde **type_info::before** adres-of için benzer **(&)** işleci.  
  
 **Type_info::name** üye işlevinin döndürdüğü bir **const char\***  türünün okunabilir adını temsil eden bir null ile sonlandırılmış dizeye. İşaret edilen bellek önbelleğe alınır ve hiçbir zaman doğrudan kaldırılmamalıdır.  
  
 **Type_info::raw_name** üye işlevinin döndürdüğü bir **const char\***  nesne türü düzenlenmiş adını temsil eden bir null ile sonlandırılmış dizeye. Ad aslında yerden kazanmak için düzenlenmiş hâli içinde saklanır. Sonuç olarak, bu işlev hızlıdır **type_info::name** adı bilgilerini kaldırmak gerekli olmayan olduğundan. Tarafından döndürülen dize **type_info::raw_name** işlevi karşılaştırma işlemlerinde kullanışlıdır ancak okunabilir değil. Okunabilir dize gerekiyorsa kullanın **type_info::name** yerine işlev.  
  
 Tür bilgilerini çok biçimli sınıflar serileştirilebilmesi için oluşturulan [/GR (çalışma zamanı türü bilgileri etkinleştir)](../build/reference/gr-enable-run-time-type-information.md) derleyici seçeneği belirtildi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Tür Bilgileri](../cpp/run-time-type-information.md)
