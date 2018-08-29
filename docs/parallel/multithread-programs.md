---
title: Çoklu iş parçacığı kullanan programlar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- threading [C++], about threading
- multithreading [C++], about threads
ms.assetid: 02443596-f7e1-48d0-b3a4-39ee0e54e444
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25debffcd667c7e0d7405d0a4454b60729825fcb
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/28/2018
ms.locfileid: "43131291"
---
# <a name="multithread-programs"></a>Çoklu İş Parçacığı Kullanan Programlar
Bir iş parçacığı bir program aracılığıyla yürütmenin temel bir yoludur. Bu ayrıca en küçük Win32 zamanlayan birimidir. Bir iş parçacığı yığını, CPU kayıtlar ve sistem Zamanlayıcı yürütme listesindeki bir girdinin durumu oluşur. Her iş parçacığının tüm işlem kaynaklarını paylaşır.  
  
Bir işlem bir veya daha fazla iş parçacığı ve kod, veri ve diğer kaynakları bellekte bir programın oluşur. Programın normal dinamik olarak ayrılan bellek açık dosyalar ve semaforları kaynaklardır. Bir program, sistem Zamanlayıcı bir iş parçacıklarını yürütme denetimi verdiğinde yürütür. Zamanlayıcı iş parçacıklarının hangilerinin ve ne zaman çalışması gerektiğini belirler. Düşük öncelikli iş parçacıklarının yüksek öncelikli iş parçacıklarının görevlerini tamamlamak bekleyin gerekebilir. Çok işlemcili makinelerde Zamanlayıcı, tek tek iş parçacığı CPU yükü dengelemek için farklı işlemcilere taşıyabilirsiniz.  
  
Bir işlemdeki her iş parçacığı bağımsız olarak çalışır. Bunları birbirine görünür yaptığınız sürece, iş parçacıkları tek tek yürütün ve diğer iş parçacığı bir işlemdeki farkında değildir. Ortak kaynakları paylaşma iş parçacıkları ancak iş parçacıklarıyla veya işlemler arası iletişim başka bir yöntem kullanılarak koordine etmeleri gerekir. İş parçacıklarını eşitleme hakkında daha fazla bilgi için bkz. [bir çoklu iş parçacığı kullanan Win32 programı yazma](writing-a-multithreaded-win32-program.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[C ve Win32 ile Çoklu İş Parçacığı Kullanımı](multithreading-with-c-and-win32.md)