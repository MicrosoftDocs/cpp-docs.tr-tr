---
title: Bağlayıcı araçları hatası LNK2017 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2017
dev_langs:
- C++
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 095423b5f2d86cef309ed4316ff72d195b11eb26
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33313078"
---
# <a name="linker-tools-error-lnk2017"></a>Bağlayıcı Araçları Hatası LNK2017
'kesimine' /LARGEADDRESSAWARE:NO geçersiz 'simgesi' yeniden konumlandırma  
  
 32-bit adresleriyle 64 bit bir görüntü oluşturmaya çalışıyorsunuz. Bunu yapmak için şunları yapmalısınız:  
  
-   Bir sabit yük adresi kullanın.  
  
-   Görüntü 3 GB kısıtlayın.  
  
-   Belirtin [/largeaddressaware:no](../../build/reference/largeaddressaware-handle-large-addresses.md).