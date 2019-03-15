---
title: LIBRARY
ms.date: 11/04/2016
f1_keywords:
- LIBRARY
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
ms.openlocfilehash: b43f269726e8925abeefd41aab0edfd57b071035
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811790"
---
# <a name="library"></a>LIBRARY

Bir DLL'yi oluşturmak için bağlantı söyler. .Exp dosyasının yapı kullanılmadığı sürece aynı anda içeri aktarma kitaplığı, bağlantı oluşturur.

```
LIBRARY [library][BASE=address]
```

## <a name="remarks"></a>Açıklamalar

*Kitaplığı* bağımsız değişkeni, DLL Dosyasının adını belirtir. Ayrıca [/OUT](out-output-file-name.md) DLL'nin çıkış adı belirtmek için bağlayıcı seçeneği.

TEMEL =*adresi* bağımsız değişkeni, işletim sistemi DLL'yi kullanan temel adres ayarlar. Bu bağımsız değişken, 0x10000000 varsayılan DLL konumunu geçersiz kılar. Açıklamasını görmek [/BASE](base-base-address.md) temel adresler hakkındaki ayrıntılar için seçeneği.

Kullanmayı unutmayın [/dll](dll-build-a-dll.md) yapılandırdığınızda, bir DLL bağlayıcı seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[Modül Tanımlama Deyimleri Kuralları](rules-for-module-definition-statements.md)
