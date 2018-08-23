---
title: İş parçacığı denetimi için C çalışma zamanı kitaplığı işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _beginthread function
- _endthread function
- threading [C++], controlling threads
- multithreading [C++], controlling threads
- _beginthreadex function
- _endthreadex function
ms.assetid: 39d0529c-c392-4c6f-94f5-105d1e8054e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a08ba6c5343fda19bab823b9a415db18b745e2a
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2018
ms.locfileid: "42464867"
---
# <a name="c-run-time-library-functions-for-thread-control"></a>İş Parçacığı Denetimi için C Çalışma Süresi Kitaplık İşlevleri
Win32 programlar en az bir iş parçacığı vardır. Herhangi bir iş parçacığı ek iş parçacıkları oluşturabilirsiniz. Bir iş parçacığı işini hızla tamamlayın ve ardından sonlandırın veya program süresince etkin kalabilir.  
  
İş parçacığı oluşturma ve sonlandırma için LIBCMT ve MSVCRT C çalışma zamanı kitaplıkları aşağıdaki işlevleri sağlar: [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md) ve [_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md).  
  
`_beginthread` Ve `_beginthreadex` işlevleri yeni bir iş parçacığı ve işlem başarılı olursa, bir iş parçacığı tanıtıcısını döndürür. Yürütme tamamlanmadan ya da bunu kendi çağrısı ile sonlandırabilirsiniz iş parçacığı sonlanır `_endthread` veya `_endthreadex`.  
  
> [!NOTE]
> C çalışma zamanı yordamları Libcmt.lib ile bir programdan çağırmak için kullanacaksanız, iş parçacıkları ile başlamalıdır `_beginthread` veya `_beginthreadex` işlevi. Win32 işlevleri kullanmayın `ExitThread` ve `CreateThread`. Kullanarak `SuspendThread` birden fazla iş parçacığının askıya alınmış iş parçacığı C çalışma zamanı veri yapısı erişimini tamamlanması için beklerken engellendiğinde bir kilitlenmesine yol açabilir.  
  
##  <a name="_core_the__beginthread_function"></a> _Beginthread ve _beginthreadex işlevleri  
 
`_beginthread` Ve `_beginthreadex` İşlevler, yeni bir dizi oluşturun. Bir iş parçacığı bir işlem kodu ve veri bölümleri işlemdeki diğer iş parçacıkları paylaşır, ancak kendi benzersiz yazmaç değerlerini, yığın alanı ve geçerli yönerge adresi vardır. Sistem, CPU süresi her iş parçacığı verir, böylece bir işlemdeki tüm iş parçacıklarının eşzamanlı olarak yürütebilir.  
  
`_beginthread` ve `_beginthreadex` benzer [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) Win32 API işlevi, ancak bu farklılıkları vardır:  
  
- Bunlar, belirli C çalışma zamanı kitaplığı değişkenlerini başlatın. Bu seçenek, yalnızca C çalışma zamanı kitaplığı, iş parçacıklarının kullanırsanız önemlidir.  
  
- `CreateThread` yardımcı güvenlik öznitelikleri üzerinde denetim sağlayın. Bir iş parçacığını askıya alınmış durumda başlatmak için bu işlevi kullanabilirsiniz.  
  
 `_beginthread` ve `_beginthreadex` bir hata olduğunda başarılı olursa yeni iş parçacığı veya bir hata kodu için bir tanıtıcı döndürür.  
  
##  <a name="_core_the__endthread_function"></a> _Endthread ve _endthreadex işlevleri  
 
[_Endthread](../c-runtime-library/reference/endthread-endthreadex.md) işlevi tarafından oluşturulan bir iş parçacığı sonlandırır `_beginthread` (ve benzer şekilde, `_endthreadex` tarafından oluşturulan bir iş parçacığı sonlandırıldığında `_beginthreadex`). İş parçacıkları tamamladığınızda, otomatik olarak sonlandır. `_endthread` ve `_endthreadex` bir iş parçacığı koşullu sonlandırma için kullanışlıdır. İletişim bağlantı noktası denetim alınamıyor ise işleme, iletişim için adanmış bir iş parçacığı gibi çıkabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[C ve Win32 ile Çoklu İş Parçacığı Kullanımı](../parallel/multithreading-with-c-and-win32.md)