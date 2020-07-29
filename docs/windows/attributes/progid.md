---
title: Progıd (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.progid
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
ms.openlocfilehash: 3092111236afe1e1360a2814c3091ab0de4ff6ea
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213859"
---
# <a name="progid"></a>progid

COM nesnesi için ProgID belirtir.

## <a name="syntax"></a>Söz dizimi

```cpp
[ progid(name) ];
```

### <a name="parameters"></a>Parametreler

*ada*<br/>
Nesneyi temsil eden ProgID.

ProgID 'ler, COM/ActiveX nesnelerini tanımlamak için kullanılan sınıf tanımlayıcısının (CLSID) okunabilir bir sürümünü sunar.

## <a name="remarks"></a>Açıklamalar

`progid`C++ özniteliği BIR com nesnesi Için ProgID belirtmenize imkan sağlar. Bir ProgID *name1. AD2. Version*biçiminde bulunur. Bir ProgID için *Sürüm* belirtmezseniz, varsayılan sürüm 1 ' dir. *Name1. AD2*belirtmezseniz, varsayılan ad *ClassName. ClassName*olur. Belirtmezseniz `progid` ve belirtirseniz `vi_progid` , *name1. AD2* ' dan alınır `vi_progid` ve (sonraki sıralı sayı) sürümü eklenir.

Kullanan bir öznitelik bloğu `progid` da kullanmıyorsa `uuid` , derleyici, `uuid` belirtilen için mevcut olup olmadığını görmek için kayıt defterini kontrol eder `progid` . `progid`Belirtilmezse, bir oluşturmak için sürüm (ve bir coclass oluşturma kullanılıyorsa coclass adı) kullanılır `progid` .

`progid`özniteliğini belirtir `coclass` , yani belirtirseniz, `progid` ve özniteliklerini belirterek aynı şey olur `coclass` `progid` .

`progid`Öznitelik, bir sınıfın belirtilen ad altında otomatik olarak kaydedilmesine neden olur. Oluşturulan. IDL dosyası bu `progid` değeri görüntülemez.

Bu öznitelik, ATL kullanan bir proje içinde kullanıldığında, öznitelik davranışı değişir. Yukarıdaki davranışa ek olarak, Bu öznitelikle belirtilen bilgiler, `GetProgID` özniteliği tarafından eklenen işlevinde kullanılır `coclass` . Daha fazla bilgi için bkz. [coclass](coclass.md) özniteliği.

## <a name="example"></a>Örnek

Örnek kullanımı için [coclass](coclass.md) örneğine bakın `progid` .

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Şunlara uygulanır**|`class`, `struct`|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[ProgID anahtarı](/windows/win32/com/-progid--key)
