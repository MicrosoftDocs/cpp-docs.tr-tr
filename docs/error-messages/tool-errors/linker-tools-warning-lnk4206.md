---
title: "Bağlayıcı araçları uyarısı LNK4206 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4206
dev_langs: C++
helpviewer_keywords: LNK4206
ms.assetid: 6c108e33-00cf-4c5a-830d-d65d470930a7
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1227cd792065198a3cd7f7a684e51e7c87452e77
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4206"></a>Bağlayıcı Araçları Uyarısı LNK4206
önceden derlenmiş türü bilgileri; bulunamadı 'filename' bağlantılı veya üzerine değil; hata ayıklama bilgileri gibi nesne bağlama  
  
 İle derlenmiş belirli nesne dosyası [/Yc](../../build/reference/yc-create-precompiled-header-file.md), ya da bağlantı komutunda belirtilmedi veya yazıldı.  
  
 Bu uyarı için yaygın bir senaryo /Yc ile derlenen .obj kitaplığa olduğunda ve bu .obj kodunuzdan hiçbir sembol başvuruları olduğu ' dir.  Bu durumda, bağlayıcı kullanın (veya hatta bakın) .obj dosya değil.  Bu durumda, kodunuzu derleyin ve kullanmalısınız [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) kalan nesneleri (/Yc ile derlenmemiş nesneleri) için.