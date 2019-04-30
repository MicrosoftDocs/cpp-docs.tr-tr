---
title: Çoklu İş Parçacığı Kullanan Programlar
ms.date: 11/04/2016
helpviewer_keywords:
- threading [C++], about threading
- multithreading [C++], about threads
ms.assetid: 02443596-f7e1-48d0-b3a4-39ee0e54e444
ms.openlocfilehash: fd10893ecd33d39b531b9451dec708ea31c121d4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407828"
---
# <a name="multithread-programs"></a>Çoklu İş Parçacığı Kullanan Programlar

Bir iş parçacığı bir program aracılığıyla yürütmenin temel bir yoludur. Bu ayrıca en küçük Win32 zamanlayan birimidir. Bir iş parçacığı yığını, CPU kayıtlar ve sistem Zamanlayıcı yürütme listesindeki bir girdinin durumu oluşur. Her iş parçacığının tüm işlem kaynaklarını paylaşır.

Bir işlem bir veya daha fazla iş parçacığı ve kod, veri ve diğer kaynakları bellekte bir programın oluşur. Programın normal dinamik olarak ayrılan bellek açık dosyalar ve semaforları kaynaklardır. Bir program, sistem Zamanlayıcı bir iş parçacıklarını yürütme denetimi verdiğinde yürütür. Zamanlayıcı iş parçacıklarının hangilerinin ve ne zaman çalışması gerektiğini belirler. Düşük öncelikli iş parçacıklarının yüksek öncelikli iş parçacıklarının görevlerini tamamlamak bekleyin gerekebilir. Çok işlemcili makinelerde Zamanlayıcı, tek tek iş parçacığı CPU yükü dengelemek için farklı işlemcilere taşıyabilirsiniz.

Bir işlemdeki her iş parçacığı bağımsız olarak çalışır. Bunları birbirine görünür yaptığınız sürece, iş parçacıkları tek tek yürütün ve diğer iş parçacığı bir işlemdeki farkında değildir. Ortak kaynakları paylaşma iş parçacıkları ancak iş parçacıklarıyla veya işlemler arası iletişim başka bir yöntem kullanılarak koordine etmeleri gerekir. İş parçacıklarını eşitleme hakkında daha fazla bilgi için bkz. [bir çoklu iş parçacığı kullanan Win32 programı yazma](writing-a-multithreaded-win32-program.md).

## <a name="see-also"></a>Ayrıca bkz.

[C ve Win32 ile Çoklu İş Parçacığı Kullanımı](multithreading-with-c-and-win32.md)
