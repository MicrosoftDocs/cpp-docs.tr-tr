---
title: RDX (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.rdx
helpviewer_keywords:
- rdx attribute
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
ms.openlocfilehash: 2790c3de01d21242daee73fc442ad22d88739355
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023886"
---
# <a name="rdx"></a>rdx

Bir kayıt defteri anahtarı oluşturur veya mevcut bir kayıt defteri anahtarı değiştirir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ rdx(key, valuename=NULL, regtype) ]
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Açılan veya oluşturulacak anahtar adı.

*değer adı*<br/>
(İsteğe bağlı) Ayarlanacak değer alanını belirtir. Bu ada sahip bir değer alanı anahtarı zaten mevcut değilse eklenir.

*regtype*<br/>
Eklenen kayıt defteri anahtarı türü. Aşağıdakilerden biri olabilir: `text`, `dword`, `binary`, veya `CString`.

## <a name="remarks"></a>Açıklamalar

**Rdx** C++ öznitelik oluşturur veya mevcut bir kayıt defteri anahtarı bir COM bileşeni için değiştirir. Öznitelik BEGIN_RDX_MAP makrosu hedef üye uygulayan nesneye ekler. `RegistryDataExchange`, BEGIN_RDX_MAP makronun sonucu olarak, eklenen bir işlev, kayıt defteri ve veri üyeleri arasında veri aktarmak için kullanılabilir

Bu öznitelik ile birlikte kullanılabilir [coclass'ı](coclass.md), [ProgID](progid.md), veya [vi_progid](vi-progid.md) öznitelikleri veya bunlardan birini gelir diğer öznitelikleri.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|**sınıf** veya **yapı** üyesi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="example"></a>Örnek

Aşağıdaki kod, MyValue CMyClass COM bileşeni açıklayan sisteme adlı bir kayıt defteri anahtarı ekler.

```cpp
// cpp_attr_ref_rdx.cpp
// compile with: /LD /link /OPT:NOREF
#define _ATL_ATTRIBUTES
#include "atlbase.h"

[module (name="MyLib")];

class CMyClass {
public:
   CMyClass() {
      strcpy_s(m_sz, "SomeValue");
   }

   [ rdx(key = "HKCR\\MyApp.MyApp.1", valuename = "MyValue", regtype = "text")]
   char m_sz[256];
};
```

## <a name="see-also"></a>Ayrıca bkz.

[COM Öznitelikleri](com-attributes.md)<br/>
[registration_script](registration-script.md)