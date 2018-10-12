---
title: RDX (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.rdx
dev_langs:
- C++
helpviewer_keywords:
- rdx attribute
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ffee10ea334c6c425aa5ecd81705ef1915dc80c0
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789845"
---
# <a name="rdx"></a>rdx

Bir kayıt defteri anahtarı oluşturur veya mevcut bir kayıt defteri anahtarı değiştirir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ rdx(key, valuename=NULL, regtype) ]
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
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
|**İçin geçerlidir**|**sınıf** veya **yapı** üyesi|
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

## <a name="see-also"></a>Ayrıca Bkz.

[COM Öznitelikleri](com-attributes.md)<br/>
[registration_script](registration-script.md)  