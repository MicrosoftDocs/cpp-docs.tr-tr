---
title: 'Çoklu iş parçacığı kullanımı: İş parçacıklarını sonlandırma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
f1_keywords:
- CREATE_SUSPENDED
dev_langs:
- C++
helpviewer_keywords:
- premature thread termination
- starting threads
- threading [MFC], terminating threads
- multithreading [C++], terminating threads
- threading [C++], stopping threads
- terminating threads
- stopping threads
- AfxEndThread method
ms.assetid: 4c0a8c6d-c02f-456d-bd02-0a8c8d006ecb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bdf9376e9f8c9e9d74d88d0bef40dc71fd43d51f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="multithreading-terminating-threads"></a>Çoklu İş Parçacığı Kullanımı: İş Parçacıklarını Sonlandırma
İki normal durum iş parçacığının sonlandırılmasına neden: denetleyen işlev çıkar veya iş parçacığının tamamlanıncaya kadar çalışabilmesi için izin verilmiyor. Sözcük işlemci arka plan yazdırması için bir iş parçacığı kullandıysanız, denetleme normalde başarıyla tamamlanmış yazdırma sonlandırma işlevi. Ancak, kullanıcı yazdırmayı iptal etmek istiyorsa, erken sona erdirilecek arka plan yazdırma iş parçacığı vardır. Bu konu, her durumun nasıl uygulanacağını ve sonlandırıldıktan sonra bir iş parçacığı çıkış kodunu alma açıklar.  
  
-   [Normal iş parçacığı sonlandırma](#_core_normal_thread_termination)  
  
-   [Erken iş parçacığı sonlandırma](#_core_premature_thread_termination)  
  
-   [Bir iş parçacığı çıkış kodunu alma](#_core_retrieving_the_exit_code_of_a_thread)  
  
##  <a name="_core_normal_thread_termination"></a> Normal iş parçacığı sonlandırma  
 Bir çalışan iş parçacığı için normal iş parçacığı sonlandırma basittir: denetleyen işlev çıkın ve sonlandırma sebebini bir değer döndürür. Kullanabilirsiniz [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) işlevi veya `return` deyimi. Genellikle, 0 başarılı tamamlamayı belirtir, ancak size kalmıştır.  
  
 Bir kullanıcı arabirimi iş parçacığı için işlem gayet basittir: kullanıcı arabirimi iş parçacığı içinde çağırmanıza [PostQuitMessage](http://msdn.microsoft.com/library/windows/desktop/ms644945) içinde [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]. Tek parametre, **PostQuitMessage** alır, iş parçacığının çıkış kodudur. İşçi iş parçacıkları için 0 genellikle başarılı tamamlamayı belirtir.  
  
##  <a name="_core_premature_thread_termination"></a> Erken iş parçacığı sonlandırma  
 Bir iş parçacığı erken sonlandırma neredeyse basittir: çağrı [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) gelen iş parçacığı içinde. İstenen çıkış kodu tek parametre olarak geçirin. Bu iş parçacığının çalışmayı durdurur, iş parçacığının yığınını kaldırır, iş parçacığına eklenmiş tüm DLL'leri ayırır ve bellekten iş parçacığı nesneyi siler.  
  
 `AfxEndThread` Sonlandırılacak iş parçacığı içinde çağrılmalıdır. Bir iş parçacığından başka bir iş parçacığı sonlandırma istiyorsanız, iki iş parçacıkları arasında iletişim yöntemini ayarlamanız gerekir.  
  
##  <a name="_core_retrieving_the_exit_code_of_a_thread"></a> Bir iş parçacığı çıkış kodunu alma  
 Çalışan ya da kullanıcı arabirimi iş parçacığı çıkış kodu almak için arama [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190) işlevi. Bu işlev hakkında daha fazla bilgi için bkz: [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]. Bu işlev tanıtıcısı iş parçacığı alır (depolanan `m_hThread` veri üyesi `CWinThread` nesneler) ve adresini bir `DWORD`.  
  
 İş parçacığı hala etkin ise **GetExitCodeThread** yerleştirir **STILL_ACTIVE** sağlanan içinde `DWORD` adres; Aksi takdirde, bu adres çıkış kodu yerleştirilir.  
  
 Çıkış kodunu alma [CWinThread](../mfc/reference/cwinthread-class.md) nesneleri fazladan bir adım alır. Varsayılan olarak, bir `CWinThread` iş parçacığı sonlandırıldığında, iş parçacığı nesnesi silinir. Bu erişemeyeceğiniz anlamına gelir `m_hThread` veri üyesi olduğundan `CWinThread` nesnesi artık yok. Bu durumu önlemek için aşağıdakilerden birini yapın:  
  
-   Ayarlama `m_bAutoDelete` veri üyesini **FALSE**. Böylece `CWinThread` iş parçacığı sonlandırıldıktan sonra varlığını sürdürmesi için nesne. Daha sonra erişebilirsiniz `m_hThread` iş parçacığı sonlandırıldıktan sonra veri üyesi. Bu yöntemi kullanırsanız, ancak yok etme için sorumlu olduğunuz `CWinThread` framework otomatik olarak onu sizin için silmez çünkü nesne. Bu tercih edilen yöntemdir.  
  
-   İş parçacığının işleyicilerini ayrı saklayın. İş parçacığı oluşturulduktan sonra kopyalama, `m_hThread` veri üyesi (kullanarak **:: DuplicateHandle**) başka bir değişkene ve değişken üzerinden erişebilirsiniz. Bu şekilde nesne sonlandırma gerçekleşir ve iş parçacığının neden yine de bulabilirsiniz otomatik olarak silinir. Tanıtıcı çoğaltabilirsiniz önce iş parçacığı sonlandırma değil, dikkat edin. Bunu yapmak için en güvenli yolu geçirmektir **AfxBeginThread'e** için [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), tanıtıcı depolamak ve ardından iş parçacığını çağırarak devam [ResumeThread'i](../mfc/reference/cwinthread-class.md#resumethread).  
  
 Nedenini belirlemek her iki yöntem sayesinde bir `CWinThread` nesne sonlandırıldı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ ve MCF ile çoklu iş parçacığı kullanımı](../parallel/multithreading-with-cpp-and-mfc.md)   
 [_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)   
 [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659)