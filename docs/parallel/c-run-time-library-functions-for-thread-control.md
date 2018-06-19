---
title: C çalışma zamanı kitaplığı işlevleri için iş parçacığı denetimi | Microsoft Docs
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
ms.openlocfilehash: 4a505bae156edba6798812b807d7ab5c6ea9e396
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33685768"
---
# <a name="c-run-time-library-functions-for-thread-control"></a>İş Parçacığı Denetimi için C Çalışma Süresi Kitaplık İşlevleri
Tüm Win32 programlar en az bir iş parçacığı vardır. Hiçbir iş parçacığı ek iş parçacığı oluşturabilirsiniz. Bir iş parçacığı çalışmasını hızlı bir şekilde tamamlayın ve ardından sonlandırmak ya da program yaşam süreleri boyunca etkin kalabilir.  
  
 İş parçacığı oluşturma ve sonlandırma için LIBCMT ve MSVCRT C çalışma zamanı kitaplıkları aşağıdaki işlevleri sağlar: [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md) ve [_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md).  
  
 `_beginthread` Ve `_beginthreadex` işlevleri yeni bir iş parçacığı ve işlem başarılı olursa bir iş parçacığı tanımlayıcısı döndürür. Yürütme tamamlandığında veya kendisi çağrısıyla sonlandırmak iş parçacığı otomatik olarak sonlandırır `_endthread` veya `_endthreadex`.  
  
> [!NOTE]
>  C çalışma zamanı yordamları Libcmt.lib ile bir programdan çağırmak için kullanacaksanız, iş parçacığı ile başlamalıdır `_beginthread` veya `_beginthreadex` işlevi. Win32 işlevleri kullanmayın `ExitThread` ve `CreateThread`. Kullanarak `SuspendThread` birden çok iş parçacığı bir C çalışma zamanı veri yapısı erişimini tamamlamak askıya alınmış iş parçacığı için beklerken engellendiğinde bir kilitlenmeye neden olabilir.  
  
##  <a name="_core_the__beginthread_function"></a> _Beginthread ve _beginthreadex işlevleri  
 `_beginthread` Ve `_beginthreadex` işlevleri yeni bir iş parçacığı oluşturma. Bir iş parçacığı işlemindeki başka bir iş parçacığı ile bir işlem kodu ve veri parçalarını paylaşır, ancak kendi benzersiz kayıt değerlerini, yığın alanı ve geçerli yönerge adresi vardır. Bir işlemdeki tüm iş parçacıklarını eşzamanlı olarak çalıştırabilmeniz için sistemi her iş parçacığı için CPU süresi sağlar.  
  
 `_beginthread` ve `_beginthreadex` benzer [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) Win32 API işlevinde, ancak bu farklılıklar vardır:  
  
-   Bunlar belirli C çalışma zamanı kitaplığı değişkenleri başlatır. Bu, iş parçacıkları C çalışma zamanı kitaplığı kullanıyorsanız önemlidir.  
  
-   `CreateThread` yardımcı güvenlik öznitelikleri üzerinde denetim sağlar. Bir iş parçacığı askıya alınmış durumda başlatmak için bu işlevi kullanabilirsiniz.  
  
 `_beginthread` ve `_beginthreadex` bir hata olduğunda bir tanıtıcı yeni iş parçacığı başarılı olursa ya da bir hata kodu döndürür.  
  
##  <a name="_core_the__endthread_function"></a> _Endthread ve _endthreadex işlevleri  
 [_Endthread](../c-runtime-library/reference/endthread-endthreadex.md) işlevi tarafından oluşturulan bir iş parçacığı sonlandırır `_beginthread` (ve benzer şekilde, `_endthreadex` tarafından oluşturulan bir iş parçacığını sonlandırır `_beginthreadex`). İş parçacığı, bunlar tamamladığınızda otomatik olarak sonlanır. `_endthread` ve `_endthreadex` bir iş parçacığından koşullu sonlandırma için faydalıdır. İletişim bağlantı noktası denetim elde kaydedemediği işleme, iletişim için adanmış bir iş parçacığı Örneğin, çıkabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C ve Win32 ile Çoklu İş Parçacığı Kullanımı](../parallel/multithreading-with-c-and-win32.md)