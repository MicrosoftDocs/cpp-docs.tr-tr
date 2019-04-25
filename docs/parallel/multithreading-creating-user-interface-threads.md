---
title: 'Çoklu iş parçacığı kullanımı: MFC kullanıcı arabirimi iş parçacıkları oluşturma'
ms.date: 08/27/2018
f1_keywords:
- CREATE_SUSPENDED
- SECURITY_ATTRIBUTES
helpviewer_keywords:
- multithreading [C++], user interface threads
- threading [C++], creating threads
- threading [C++], user interface threads
- user interface threads [C++]
- threading [MFC], user interface threads
ms.assetid: 446925c1-db59-46ea-ae5b-d5ae5d5b91d8
ms.openlocfilehash: ac22fad95041b07e132d31a2d246e58c3b40d30c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62212915"
---
# <a name="multithreading-creating-mfc-user-interface-threads"></a>Çoklu iş parçacığı kullanımı: MFC kullanıcı arabirimi iş parçacıkları oluşturma

Bir kullanıcı arabirimi iş parçacığı, genellikle kullanıcı girişlerini işler ve uygulamanın diğer kısımlarını çalışan iş parçacıklarının bağımsız olarak kullanıcı olayları yanıtlamak için kullanılır. Ana uygulama iş parçacığı (sağlanan, `CWinApp`-türetilmiş sınıf) zaten oluşturulur ve sizin için başlatıldı. Bu konu, ek kullanıcı arabirimi iş parçacığı oluşturmak gereken adımları açıklar.

Bir kullanıcı arabirimi iş parçacığı oluşturulurken gerçekleştirmelisiniz ilk öğesinden bir sınıf türetin şeydir [CWinThread](../mfc/reference/cwinthread-class.md). Bildirme ve bunu kullanarak sınıf [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate) ve [IMPLEMENT_DYNCREATE](../mfc/reference/run-time-object-model-services.md#implement_dyncreate) makroları. Bu sınıf, bazı işlevler geçersiz kılmanız gerekir ve diğerlerini geçersiz kılabilir. Aşağıdaki tabloda, bu işlevler ve bunların ne yapması gerektiğini sunulur.

### <a name="functions-to-override-when-creating-a-user-interface-thread"></a>Bir kullanıcı arabirimi iş parçacığı oluşturulurken geçersiz kılmak için işlevleri

|İşlev|Amaç|
|--------------|-------------|
|[ExitInstance](../mfc/reference/cwinthread-class.md#exitinstance)|İş parçacığı sonlandığında temizleme işlemi gerçekleştirin. Genellikle geçersiz kılınmış.|
|[InitInstance](../mfc/reference/cwinthread-class.md#initinstance)|İş parçacığı örneği başlatma gerçekleştirin. Geçersiz kılınmalıdır.|
|[ONIDLE](../mfc/reference/cwinthread-class.md#onidle)|İş parçacığına özgü boşta kalma süresi işlemini gerçekleştirin. Genellikle geçersiz kılınmaz.|
|[PreTranslateMessage](../mfc/reference/cwinthread-class.md#pretranslatemessage)|İletileri için dağıtılmadan önce filtrelemek `TranslateMessage` ve `DispatchMessage`. Genellikle geçersiz kılınmaz.|
|[ProcessWndProcException](../mfc/reference/cwinthread-class.md#processwndprocexception)|İş parçacığının ve ileti işleyici tarafından oluşturulan yakalanamayan özel durum uğratabilir. Genellikle geçersiz kılınmaz.|
|[Çalıştır](../mfc/reference/cwinthread-class.md#run)|Denetleme işlevi iş parçacığı için. İleti pompası içerir. Nadiren geçersiz kılınmış.|

MFC sağlayan iki sürümünü `AfxBeginThread` parametresi aşırı yükleme yoluyla: biri yalnızca bir kullanıcı arabirimi iş parçacıkları veya çalışan iş parçacıkları oluşturabilirsiniz ve bir çalışan iş parçacıkları oluşturabilirsiniz. İkinci aşırı yüklemesi, kullanıcı arabirimi iş parçacığı için çağrı [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), aşağıdaki bilgileri sağlayarak:

- [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) sınıfından türetilen sınıfın `CWinThread`.

- (İsteğe bağlı) İstenen öncelik düzeyi. Varsayılan, normal önceliktir. Kullanılabilir öncelik düzeyleri hakkında daha fazla bilgi için bkz: [SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) Windows SDK.

- (İsteğe bağlı) İş parçacığının istenen yığın boyutu. Oluşturulan iş parçacığıyla aynı boyutta bir yığına varsayılandır.

- (İsteğe bağlı) CREATE_SUSPENDED iş parçacığının askıya alınmış durumda oluşturulmasını istiyorsanız. Varsayılan, 0 veya iş parçacığını normal olarak başlatın.

- (İsteğe bağlı) İstenen güvenlik öznitelikleri. Varsayılan ana iş parçacığıyla aynı erişimdir. Bu güvenlik bilgileri biçimi hakkında daha fazla bilgi için bkz. [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) Windows SDK.

`AfxBeginThread` işin çoğunu sizin için halleder. Sınıfının yeni bir nesne oluşturur, sağladığınız bilgiler ve çağrı başlatır [CWinThread::CreateThread](../mfc/reference/cwinthread-class.md#createthread) iş parçacığını yürütmeye başlamak için. Denetimleri, tüm nesnelerin düzgün bir şekilde oluşturmayı, herhangi bir bölümü başarısız olması serbest bırakıldığından emin olmak için yordam boyunca gerçekleştirilir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Çoklu iş parçacığı kullanımı: İş parçacıklarını sonlandırma](multithreading-terminating-threads.md)

- [Çoklu iş parçacığı kullanımı: Çalışan iş parçacıkları oluşturma](multithreading-creating-worker-threads.md)

- [İşlemler ve iş parçacıkları](/windows/desktop/ProcThread/processes-and-threads)

## <a name="see-also"></a>Ayrıca bkz.

[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)
