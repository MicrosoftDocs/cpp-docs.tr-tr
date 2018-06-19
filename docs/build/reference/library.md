---
title: KİTAPLIĞI | Microsoft Docs
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
ms.openlocfilehash: 0d2fb7e69b0557bf96601666c390b3d59412b5a0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371170"
---
# <a name="library"></a>LIBRARY
DLL oluşturmak için bağlantı söyler. Bir .exp dosyası derleme kullanılmadığı sürece aynı anda bir içeri aktarma kitaplığını bağlantı oluşturur.  
  
```  
LIBRARY [library][BASE=address]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 *Kitaplığı* bağımsız değişkeni DLL adını belirtir. Aynı zamanda [/OUT](../../build/reference/out-output-file-name.md) bağlayıcı seçeneği DLL'nin çıktı adı belirtin.  
  
 TEMEL =*adresi* bağımsız değişkeni DLL yüklemek için işletim sisteminin kullandığı temel adresini ayarlar. Bu bağımsız değişken 0x10000000 varsayılan DLL konumu geçersiz kılar. Açıklamasını görmek [/temel](../../build/reference/base-base-address.md) seçeneği temel adresler hakkında ayrıntılı bilgi için.  
  
 Kullanmayı unutmayın [/dll](../../build/reference/dll-build-a-dll.md) DLL derlerken bağlayıcı seçeneği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Modül Tanımlama Deyimleri Kuralları](../../build/reference/rules-for-module-definition-statements.md)