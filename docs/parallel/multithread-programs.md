---
title: Çoklu İş Parçacığı Kullanan Programlar
ms.date: 11/04/2016
helpviewer_keywords:
- threading [C++], about threading
- multithreading [C++], about threads
ms.assetid: 02443596-f7e1-48d0-b3a4-39ee0e54e444
ms.openlocfilehash: 0b79fe84fbf7d910d53cb5bc333668b7d99ab8ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502057"
---
# <a name="multithread-programs"></a>Çoklu İş Parçacığı Kullanan Programlar

Bir iş parçacığı bir program aracılığıyla yürütmenin temel bir yoludur. Bu ayrıca en küçük Win32 zamanlayan birimidir. Bir iş parçacığı yığını, CPU kayıtlar ve sistem Zamanlayıcı yürütme listesindeki bir girdinin durumu oluşur. Her iş parçacığının tüm işlem kaynaklarını paylaşır.

Bir işlem bir veya daha fazla iş parçacığı ve kod, veri ve diğer kaynakları bellekte bir programın oluşur. Programın normal dinamik olarak ayrılan bellek açık dosyalar ve semaforları kaynaklardır. Bir program, sistem Zamanlayıcı bir iş parçacıklarını yürütme denetimi verdiğinde yürütür. Zamanlayıcı iş parçacıklarının hangilerinin ve ne zaman çalışması gerektiğini belirler. Düşük öncelikli iş parçacıklarının yüksek öncelikli iş parçacıklarının görevlerini tamamlamak bekleyin gerekebilir. Çok işlemcili makinelerde Zamanlayıcı, tek tek iş parçacığı CPU yükü dengelemek için farklı işlemcilere taşıyabilirsiniz.

Bir işlemdeki her iş parçacığı bağımsız olarak çalışır. Bunları birbirine görünür yaptığınız sürece, iş parçacıkları tek tek yürütün ve diğer iş parçacığı bir işlemdeki farkında değildir. Ortak kaynakları paylaşma iş parçacıkları ancak iş parçacıklarıyla veya işlemler arası iletişim başka bir yöntem kullanılarak koordine etmeleri gerekir. İş parçacıklarını eşitleme hakkında daha fazla bilgi için bkz. [bir çoklu iş parçacığı kullanan Win32 programı yazma](writing-a-multithreaded-win32-program.md).

## <a name="see-also"></a>Ayrıca Bkz.

[C ve Win32 ile Çoklu İş Parçacığı Kullanımı](multithreading-with-c-and-win32.md)