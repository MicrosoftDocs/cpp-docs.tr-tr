---
title: LIBRARY
ms.date: 11/04/2016
f1_keywords:
- LIBRARY
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
ms.openlocfilehash: 73609be698719da05fff357ba80200c49f598add
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422678"
---
# <a name="library"></a>LIBRARY

Bir DLL'yi oluşturmak için bağlantı söyler. .Exp dosyasının yapı kullanılmadığı sürece aynı anda içeri aktarma kitaplığı, bağlantı oluşturur.

```
LIBRARY [library][BASE=address]
```

## <a name="remarks"></a>Açıklamalar

*Kitaplığı* bağımsız değişkeni, DLL Dosyasının adını belirtir. Ayrıca [/OUT](../../build/reference/out-output-file-name.md) DLL'nin çıkış adı belirtmek için bağlayıcı seçeneği.

TEMEL =*adresi* bağımsız değişkeni, işletim sistemi DLL'yi kullanan temel adres ayarlar. Bu bağımsız değişken, 0x10000000 varsayılan DLL konumunu geçersiz kılar. Açıklamasını görmek [/BASE](../../build/reference/base-base-address.md) temel adresler hakkındaki ayrıntılar için seçeneği.

Kullanmayı unutmayın [/dll](../../build/reference/dll-build-a-dll.md) yapılandırdığınızda, bir DLL bağlayıcı seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[Modül Tanımlama Deyimleri Kuralları](../../build/reference/rules-for-module-definition-statements.md)
