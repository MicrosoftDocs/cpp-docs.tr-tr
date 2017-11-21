---
title: ". Bağlayıcı girişi olarak Ilk dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6e7d801992beb75ccc14e185fc062dc4c51f8433
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ilk-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Ilk Dosyaları
Artımlı olarak bağlanırken bağlantı ilk artımlı bağlantı sırasında oluşturulan .ilk durum dosyası güncelleştirir. Bu dosyanın .exe veya .dll dosyası aynı temel adı ve uzantısı .ilk varsa. Sonraki artımlı bağlantılar sırasında bağlantı .ilk dosyasını güncelleştirir. .İlk dosyası eksikse, bağlantı tam bağlantısı gerçekleştirir ve yeni bir .ilk dosyası oluşturur. .İlk dosya kullanılamaz ise, bağlantı nonincremental bağlantı gerçekleştirir. Artımlı bağlantılandırma hakkında daha fazla bilgi için bkz [artımlı bağlantı (/ ARTIMLI)](../../build/reference/incremental-link-incrementally.md) seçeneği.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINK giriş dosyaları](../../build/reference/link-input-files.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)