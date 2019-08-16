---
title: Progıd (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.progid
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
ms.openlocfilehash: d529d7362dc62207cfd72576159f560a3e04c221
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514240"
---
# <a name="progid"></a>progid

COM nesnesi için ProgID belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ progid(name) ];
```

### <a name="parameters"></a>Parametreler

*name*<br/>
Nesneyi temsil eden ProgID.

ProgID 'ler, COM/ActiveX nesnelerini tanımlamak için kullanılan sınıf tanımlayıcısının (CLSID) okunabilir bir sürümünü sunar.

## <a name="remarks"></a>Açıklamalar

**ProgID** C++ özniteliği bir com nesnesi için ProgID belirtmenize olanak tanır. Bir ProgID *name1. AD2. Version*biçiminde bulunur. Bir ProgID için *Sürüm* belirtmezseniz, varsayılan sürüm 1 ' dir. *Name1. AD2*belirtmezseniz, varsayılan ad *ClassName. ClassName*olur. **ProgID** belirtmezseniz ve belirtirseniz `vi_progid`, *name1. AD2* ' dan `vi_progid` alınır ve (sonraki sıralı sayı) sürümü eklenir.

**ProgID** kullanan bir öznitelik bloğu da **UUID**kullanmıyorsa, derleyici, belirtilen **ProgID**için bir **UUID** 'nin var olup olmadığını görmek için kayıt defterini kontrol eder. **ProgID** belirtilmemişse, bir **ProgID**oluşturmak için sürüm (ve coclass oluşturma kullanılıyorsa coclass adı) kullanılır.

**ProgID, özniteliğini belirtir** , yani **ProgID**belirtirseniz, `coclass` ve ProgID özniteliklerini belirten şeydir. `coclass`

**ProgID** özniteliği, bir sınıfın belirtilen ad altında otomatik olarak kaydedilmesine neden olur. Oluşturulan. IDL dosyası **ProgID** değerini görüntülemez.

Bu öznitelik, ATL kullanan bir proje içinde kullanıldığında, öznitelik davranışı değişir. Yukarıdaki davranışa ek olarak, Bu öznitelikle belirtilen bilgiler, `GetProgID` `coclass` özniteliği tarafından eklenen işlevinde kullanılır. Daha fazla bilgi için bkz. [coclass](coclass.md) özniteliği.

## <a name="example"></a>Örnek

Örnek bir **ProgID**kullanımı için [coclass](coclass.md) örneğine bakın.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**sınıf**, **Yapı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[ProgID anahtarı](/windows/win32/com/-progid--key)
