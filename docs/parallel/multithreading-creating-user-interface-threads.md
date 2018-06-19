---
title: 'Çoklu iş parçacığı kullanımı: Kullanıcı arabirimi iş parçacıkları oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
f1_keywords:
- CREATE_SUSPENDED
- SECURITY_ATTRIBUTES
dev_langs:
- C++
helpviewer_keywords:
- multithreading [C++], user interface threads
- threading [C++], creating threads
- threading [C++], user interface threads
- user interface threads [C++]
- threading [MFC], user interface threads
ms.assetid: 446925c1-db59-46ea-ae5b-d5ae5d5b91d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 480839316cc8d47b2af4be1cd81c0d02f09fad25
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688875"
---
# <a name="multithreading-creating-user-interface-threads"></a>Çoklu İş Parçacığı Kullanımı: Kullanıcı Arabirimi İş Parçacıkları Oluşturma
Bir kullanıcı arabirimi iş parçacığı kullanıcı girişini işlemek ve diğer uygulama bölümlerini çalışan iş parçacıklarının bağımsız olarak kullanıcı olaylarına tepki vermek için yaygın olarak kullanılır. Ana uygulama iş parçacığı (sağlanan, `CWinApp`-türetilmiş sınıf) daha önce oluşturduğunuz ve sizin için başlatıldı. Bu konu, ek kullanıcı arabirimi iş parçacıkları oluşturmak için gereken adımları açıklar.  
  
 Bir kullanıcı arabirimi iş parçacığı oluşturulurken gerçekleştirmelisiniz ilk şey öğesinden bir sınıf türetin [CWinThread](../mfc/reference/cwinthread-class.md). Bildirme ve bunu uygulamak sınıfı, kullanarak [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate) ve [IMPLEMENT_DYNCREATE](../mfc/reference/run-time-object-model-services.md#implement_dyncreate) makroları. Bu sınıf, bazı işlevleri geçersiz kılmanız gerekir ve diğerlerini geçersiz kılabilir. Aşağıdaki tabloda, bu işlevler ve bunların ne yapması gerektiğini sunulur.  
  
### <a name="functions-to-override-when-creating-a-user-interface-thread"></a>Bir kullanıcı arabirimi iş parçacığı oluşturulurken geçersiz kılmak için işlevleri  
  
|İşlev|Amaç|  
|--------------|-------------|  

|[ExitInstance](../mfc/reference/cwinthread-class.md#exitinstance)| İş parçacığı sonlandırıldığında temizleme işlemi gerçekleştirin. Genellikle geçersiz kılınmaz. |  
|[InitInstance](../mfc/reference/cwinthread-class.md#initinstance)| İş parçacığı örneği başlatma gerçekleştirir. Geçersiz kılınmalıdır. |  
|[ONIDLE](../mfc/reference/cwinthread-class.md#onidle)| İş parçacığına özgü boşta kalma süresi işlemini gerçekleştirin. Genellikle geçersiz kılınmaz. |  
|[PreTranslateMessage](../mfc/reference/cwinthread-class.md#pretranslatemessage)| İçin dağıtılan önce iletilerine filtre **TranslateMessage** ve **DispatchMessage**. Genellikle geçersiz kılınmaz. |  
|[ProcessWndProcException](../mfc/reference/cwinthread-class.md#processwndprocexception)| İş parçacığının ileti ve komut işleyicileri tarafından oluşturulan işlenmeyen özel durumları kesebilir. Genellikle geçersiz kılınmaz. |  
|[Çalıştırma](../mfc/reference/cwinthread-class.md#run)| İş parçacığı için işlevi denetleme. İleti Pompalama içerir. Nadiren geçersiz kılındı. |  

  
 MFC sağlayan iki sürümü `AfxBeginThread` parametre aşırı: bir çalışan iş parçacıkları ve bir kullanıcı arabirimi iş parçacıkları veya çalışan iş parçacığı oluşturabilir yalnızca oluşturabilirsiniz. Kullanıcı arabirimi iş parçacığı başlatmak için ikinci aşırı yüklemesini çağırın [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), aşağıdaki bilgileri sağlar:  
  
-   [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) öğesinden türetilmiş sınıf `CWinThread`.  
  
-   (İsteğe bağlı) İstenen öncelik düzeyi. Normal öncelikli varsayılandır. Varolan öncelik düzeyleri hakkında daha fazla bilgi için bkz: [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) içinde [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
-   (İsteğe bağlı) İş parçacığı için istenen yığın boyutu. Aynı boyut yığın oluşturma iş parçacığı olarak varsayılandır.  
  
-   (İsteğe bağlı) **AfxBeginThread'e** askıya alınmış durumda oluşturulacak iş parçacığı istiyorsanız. Varsayılan değer 0'dır veya normal iş parçacığı başlatılamıyor.  
  
-   (İsteğe bağlı) İstenen güvenlik öznitelikleri. Üst iş parçacığı aynı erişim varsayılandır. Bu güvenlik bilgileri biçimi hakkında daha fazla bilgi için bkz: [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) içinde [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 `AfxBeginThread` işlerin çoğunu sizin için yapar. Sınıfının yeni bir nesne oluşturur, sağladığınız bilgileri ve çağrıları başlatır [CWinThread::CreateThread](../mfc/reference/cwinthread-class.md#createthread) iş parçacığının başlatmak için. Denetimleri prosedür boyunca tüm nesneleri düzgün herhangi bir kısmını oluşturma başarısız olması kaldırıldığından emin olmak için yapılır.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [Çoklu İş Parçacığı Kullanımı: İş Parçacıklarını Sonlandırma](../parallel/multithreading-terminating-threads.md)  
  
-   [Çoklu İş Parçacığı Kullanımı: Çalışan İş Parçacıkları Oluşturma](../parallel/multithreading-creating-worker-threads.md)  
  
-   [İşlemler ve iş parçacıkları](http://msdn.microsoft.com/library/windows/desktop/ms684841)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](../parallel/multithreading-with-cpp-and-mfc.md)