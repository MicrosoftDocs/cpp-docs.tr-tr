---
title: LIBRARY
ms.date: 11/04/2016
f1_keywords:
- LIBRARY
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
ms.openlocfilehash: f8e5fbc50551b0a44b91787f99999301a8245069
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582483"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Modül Tanımlama Deyimleri Kuralları](../../build/reference/rules-for-module-definition-statements.md)