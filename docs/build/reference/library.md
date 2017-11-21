---
title: "KİTAPLIĞI | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: LIBRARY
dev_langs: C++
helpviewer_keywords: LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 75f337f563707a1ab2b1dabe0042b678c03172e7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Modül tanımlama deyimleri kuralları](../../build/reference/rules-for-module-definition-statements.md)