---
title: Önemli hata C1510 | Microsoft Docs
ms.custom: ''
ms.date: 04/11/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1510
dev_langs:
- C++
helpviewer_keywords:
- C1510
ms.assetid: 150c827f-9514-41a9-8d7e-82f820749bcb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25b1c3f83b770dc7b346e83e9675afe423af2516
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42466177"
---
# <a name="fatal-error-c1510"></a>Önemli hata C1510
Clui.dll dil kaynağı açılamıyor  
  
 Derleyici dil kaynağı DLL yüklenemiyor.  
  
Bu sorunun iki yaygın nedenleri vardır. 32-bit derleyici ve araçları kullanarak, bağlantı sırasında 2 GB'den fazla bellek kullanan büyük projeler için bu hatayı görebilirsiniz. 64-bit Windows sistemlerinde olası bir çözüm, 64 bit yerel kullanın veya çapraz derleyici ve araçları, kod üretmek için sağlamaktır. Bu, 64-bit uygulamalar için mevcut olan daha büyük bellek alanı avantajlarından yararlanır. Bazı durumlarda bir 32-bit sistem üzerinde çalıştığından 32 bit derleyiciyi kullanmak zorundaysanız, bağlayıcı 3 GB kullanılabilir bellek miktarını artırabilir. Daha fazla bilgi için [4 gigabaytlık ayarlama: BCDEdit ve Boot.ini](https://msdn.microsoft.com/library/vs/alm/bb613473\(v=vs.85\).aspx) ve [BCDEdit/kümesi increaseuserva](https://msdn.microsoft.com/library/ff542202.aspx) komutu.  

Yaygın bir nedeni, bozuk veya eksik bir Visual Studio Yükleme ' dir. Bu durumda, Visual Studio'yu yeniden yükleyin veya yeniden onarmak için yükleyiciyi çalıştırın.  
  