---
title: KİTAPLIK | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- LIBRARY
dev_langs:
- C++
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 43b14e8e8ff4871ba4319c7f4fac5545e72e710b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723560"
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