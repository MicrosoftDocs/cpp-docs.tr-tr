---
description: 'Daha fazla bilgi edinin: KITAPLıK'
title: LIBRARY
ms.date: 11/04/2016
f1_keywords:
- LIBRARY
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
ms.openlocfilehash: 3d8c63f323568949cf2fb30935d2557755346422
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199538"
---
# <a name="library"></a>LIBRARY

Bağlantıyı bir DLL oluşturma bağlantısına söyler. Aynı zamanda, derlemede bir. exp dosyası kullanılmadığı takdirde bağlantı bir içeri aktarma kitaplığı oluşturur.

```
LIBRARY [library][BASE=address]
```

## <a name="remarks"></a>Açıklamalar

*Kitaplık* BAĞıMSıZ değişkeni dll 'in adını belirtir. Ayrıca, DLL 'nin çıkış adını belirtmek için [/Out](out-output-file-name.md) bağlayıcı seçeneğini de kullanabilirsiniz.

Taban =*Adres* bağımsız değişkeni, IŞLETIM sisteminin dll 'yi yüklemek için kullandığı temel adresi ayarlar. Bu bağımsız değişken, 0x10000000 öğesinin varsayılan DLL konumunu geçersiz kılar. Taban adresler hakkında ayrıntılar için [/Base](base-base-address.md) seçeneğinin açıklamasına bakın.

Bir DLL oluştururken [/DLL](dll-build-a-dll.md) bağlayıcı seçeneğini kullanmayı unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Module-Definition deyimleri için kurallar](rules-for-module-definition-statements.md)
