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
ms.openlocfilehash: f39a609e1621dab404ff79e49ade56a88277aa80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33199359"
---
# <a name="fatal-error-c1510"></a>Önemli hata C1510
Dil kaynak clui.dll açılamıyor  
  
 Derleyici dil kaynak DLL yüklenemiyor.  
  
Bu sorunun iki ortak nedenleri vardır. Araçlar ve 32-bit derleyici kullanırken, bu hata bağlantı sırasında 2 GB'den fazla bellek kullanır büyük projeler için görebilirsiniz. 64-bit Windows sistemlerinde olası bir çözüm 64-bit yerel kullanın veya derleyici ve kodunuzu oluşturmak için Araçlar arası şeklindedir. Bu, 64-bit uygulamaları için kullanılabilir olan daha büyük bellek alanını yararlanır. Bazı durumlarda bir 32 bit sistemde çalıştırdığınız için 32-bit derleyici kullanmanız gerekiyorsa, bağlayıcı 3 GB kullanılabilir bellek miktarını artırabilir. Daha fazla bilgi için bkz: [4 gigabaytlık ayarlama: BCDEdit ve Boot.ini](https://msdn.microsoft.com/library/vs/alm/bb613473(v=vs.85).aspx) ve [BCDEdit/set increaseuserva](https://msdn.microsoft.com/library/ff542202.aspx) komutu.  

Ortak bir nedeni bozuk veya eksik bir Visual Studio yükleme oluşturur. Bu durumda, yeniden onarmak veya Visual Studio yeniden yüklemek için yükleyiciyi çalıştırın.  
  