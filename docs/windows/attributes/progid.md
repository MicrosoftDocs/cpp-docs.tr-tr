---
description: 'Hakkında daha fazla bilgi edinin: ProgID'
title: Progıd (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.progid
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
ms.openlocfilehash: ed829d1ec20ae06fae8604e35ccc260013f59e3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114942"
---
# <a name="progid"></a>progid

COM nesnesi için ProgID belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ progid(name) ];
```

### <a name="parameters"></a>Parametreler

*ada*<br/>
Nesneyi temsil eden ProgID.

ProgID 'ler, COM/ActiveX nesnelerini tanımlamak için kullanılan sınıf tanımlayıcısının (CLSID) okunabilir bir sürümünü sunar.

## <a name="remarks"></a>Açıklamalar

`progid`C++ özniteliği BIR com nesnesi Için ProgID belirtmenize imkan sağlar. Bir ProgID *name1. AD2. Version* biçiminde bulunur. Bir ProgID için *Sürüm* belirtmezseniz, varsayılan sürüm 1 ' dir. *Name1. AD2* belirtmezseniz, varsayılan ad *ClassName. ClassName* olur. Belirtmezseniz `progid` ve belirtirseniz `vi_progid` , *name1. AD2* ' dan alınır `vi_progid` ve (sonraki sıralı sayı) sürümü eklenir.

Kullanan bir öznitelik bloğu `progid` da kullanmıyorsa `uuid` , derleyici, `uuid` belirtilen için mevcut olup olmadığını görmek için kayıt defterini kontrol eder `progid` . `progid`Belirtilmezse, bir oluşturmak için sürüm (ve bir coclass oluşturma kullanılıyorsa coclass adı) kullanılır `progid` .

`progid` özniteliğini belirtir `coclass` , yani belirtirseniz, `progid` ve özniteliklerini belirterek aynı şey olur `coclass` `progid` .

`progid`Öznitelik, bir sınıfın belirtilen ad altında otomatik olarak kaydedilmesine neden olur. Oluşturulan. IDL dosyası bu `progid` değeri görüntülemez.

Bu öznitelik, ATL kullanan bir proje içinde kullanıldığında, öznitelik davranışı değişir. Yukarıdaki davranışa ek olarak, Bu öznitelikle belirtilen bilgiler, `GetProgID` özniteliği tarafından eklenen işlevinde kullanılır `coclass` . Daha fazla bilgi için bkz. [coclass](coclass.md) özniteliği.

## <a name="example"></a>Örnek

Örnek kullanımı için [coclass](coclass.md) örneğine bakın `progid` .

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|`class`, `struct`|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[ProgID anahtarı](/windows/win32/com/-progid--key)
