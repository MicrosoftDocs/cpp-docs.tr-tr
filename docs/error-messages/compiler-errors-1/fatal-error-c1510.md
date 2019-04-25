---
title: Önemli hata C1510
ms.date: 04/11/2017
f1_keywords:
- C1510
helpviewer_keywords:
- C1510
ms.assetid: 150c827f-9514-41a9-8d7e-82f820749bcb
ms.openlocfilehash: f05f79ea78958a7d7a64f24bdce2d1151b93cdfb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208511"
---
# <a name="fatal-error-c1510"></a>Önemli hata C1510

Cannot open language resource clui.dll

Derleyici dil kaynağı DLL yüklenemiyor.

Bu sorunun iki yaygın nedenleri vardır. 32-bit derleyici ve araçları kullanarak, bağlantı sırasında 2 GB'den fazla bellek kullanan büyük projeler için bu hatayı görebilirsiniz. 64-bit Windows sistemlerinde olası bir çözüm, 64 bit yerel kullanın veya çapraz derleyici ve araçları, kod üretmek için sağlamaktır. Bu, 64-bit uygulamalar için mevcut olan daha büyük bellek alanı avantajlarından yararlanır. Bazı durumlarda bir 32-bit sistem üzerinde çalıştığından 32 bit derleyiciyi kullanmak zorundaysanız, bağlayıcı 3 GB kullanılabilir bellek miktarını artırabilir. Daha fazla bilgi için [4 gigabaytlık ayarlama: BCDEdit ve Boot.ini](https://msdn.microsoft.com/library/vs/alm/bb613473) ve [BCDEdit/kümesi increaseuserva](https://msdn.microsoft.com/library/ff542202.aspx) komutu.

Yaygın bir nedeni, bozuk veya eksik bir Visual Studio Yükleme ' dir. Bu durumda, Visual Studio'yu yeniden yükleyin veya yeniden onarmak için yükleyiciyi çalıştırın.
