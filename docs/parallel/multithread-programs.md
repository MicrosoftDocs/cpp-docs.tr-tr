---
title: "Çoklu iş parçacığı kullanan programlar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- threading [C++], about threading
- multithreading [C++], about threads
ms.assetid: 02443596-f7e1-48d0-b3a4-39ee0e54e444
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0ff73b4d3a1c8ee6971fbd3f88f491c2a5c76311
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="multithread-programs"></a>Çoklu İş Parçacığı Kullanan Programlar
Bir iş parçacığı bir program aracılığıyla yürütmenin temel bir yoludur. Bu ayrıca en küçük Win32 zamanlar yürütme birimidir. Bir iş parçacığı bir yığın CPU kaydeder ve sistem Zamanlayıcı yürütme listesinde bir girişi durumu oluşur. Her iş parçacığı tüm işlem kaynaklarını paylaşır.  
  
 Bir veya daha fazla iş parçacığı ve kodu, veri ve diğer kaynakları bellekte bir programın, bir işlem oluşur. Programın normal açık dosyalar, semafor ve dinamik olarak ayrılan bellek kaynaklardır. Sistem Zamanlayıcı parçacıklarından birine yürütme denetimi verdiğinde bir program çalıştırır. Zamanlayıcı iş parçacıklarının hangilerinin ve ne zaman çalıştırılması gerektiğini belirler. İş parçacıkları daha düşük bir öncelik yüksek öncelikli iş parçacıklarının işlerini tamamlamalarını beklemeniz gerekebilir. Çok işlemcili makinelerde Zamanlayıcı CPU yükünü dengelemek için farklı işlemcilere tek tek iş parçacığı taşıyabilirsiniz.  
  
 Bir işlemdeki her bir iş parçacığı bağımsız olarak çalışır. Birbirlerine görünür yapmanız sürece, iş parçacıklarının ayrı ayrı yürütün ve diğer iş parçacığı bir işlemde farkında değildir. Ortak kaynakları paylaşma iş parçacığı işlemler arası iletişim semaforları veya diğer kullanarak işlerine ancak koordine gerekir. İş parçacıklarını eşitleme hakkında daha fazla bilgi için bkz: [çoklu iş parçacığı kullanan Win32 programı yazma](../parallel/writing-a-multithreaded-win32-program.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C ve Win32 ile Çoklu İş Parçacığı Kullanımı](../parallel/multithreading-with-c-and-win32.md)