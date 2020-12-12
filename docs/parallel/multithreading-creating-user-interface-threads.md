---
description: 'Daha fazla bilgi edinin: çoklu iş parçacığı: MFC User-Interface Iş parçacıkları oluşturma'
title: 'Çoklu iş parçacığı kullanımı: MFC User-Interface Iş parçacıkları oluşturma'
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
ms.openlocfilehash: bb3e388918f8881fbdd1968ef953da3067904350
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149974"
---
# <a name="multithreading-creating-mfc-user-interface-threads"></a>Çoklu iş parçacığı kullanımı: MFC User-Interface Iş parçacıkları oluşturma

Kullanıcı arabirimi iş parçacığı genellikle kullanıcı girişini işlemek ve uygulamanın diğer bölümlerini yürüten iş parçacıklarından bağımsız olarak Kullanıcı olaylarına yanıt vermek için kullanılır. Ana uygulama iş parçacığı ( `CWinApp` türetilmiş sınıfınıza sunulan) zaten oluşturulur ve sizin için başlatılır. Bu konu başlığı altında, ek kullanıcı arabirimi iş parçacıkları oluşturmak için gereken adımlar açıklanmaktadır.

Kullanıcı arabirimi iş parçacığı oluştururken yapmanız gereken ilk şey, [CWinThread](../mfc/reference/cwinthread-class.md)öğesinden bir sınıf türemektir. [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate) ve [IMPLEMENT_DYNCREATE](../mfc/reference/run-time-object-model-services.md#implement_dyncreate) makrolarını kullanarak bu sınıfı bildirmeniz ve uygulamanız gerekir. Bu sınıf bazı işlevleri geçersiz kılmalıdır ve diğerlerini geçersiz kılabilir. Bu işlevler ve bunların yapması gerekenler aşağıdaki tabloda sunulmuştur.

### <a name="functions-to-override-when-creating-a-user-interface-thread"></a>User-Interface Iş parçacığı oluştururken geçersiz kılınacak işlevler

|İşlev|Amaç|
|--------------|-------------|
|[ExitInstance](../mfc/reference/cwinthread-class.md#exitinstance)|İş parçacığı sonlandırıldığında temizliği gerçekleştirin. Genellikle geçersiz kılındı.|
|[InitInstance](../mfc/reference/cwinthread-class.md#initinstance)|İş parçacığı örneğini başlatma işlemini gerçekleştirin. Geçersiz kılınmalıdır.|
|[OnIdle](../mfc/reference/cwinthread-class.md#onidle)|İş parçacığına özgü boşta kalma süresi işlemini gerçekleştirin. Genellikle geçersiz kılınmaz.|
|[PreTranslateMessage](../mfc/reference/cwinthread-class.md#pretranslatemessage)|İletileri ve ' a dağıtılmadan önce filtreleyin `TranslateMessage` `DispatchMessage` . Genellikle geçersiz kılınmaz.|
|[ProcessWndProcException](../mfc/reference/cwinthread-class.md#processwndprocexception)|İş parçacığının iletisi ve komut işleyicileri tarafından oluşturulan işlenmemiş özel durumları durdurur. Genellikle geçersiz kılınmaz.|
|[Çalıştır](../mfc/reference/cwinthread-class.md#run)|İş parçacığı için işlev denetleniyor. İleti göndericisi içerir. Nadiren geçersiz kılındı.|

MFC, `AfxBeginThread` parametre aşırı yüklemesi aracılığıyla iki sürümü sağlar: biri yalnızca çalışan iş parçacıkları ve Kullanıcı arabirimi iş parçacıkları veya çalışan iş parçacıkları oluşturabilir. Kullanıcı arabirimi iş parçacığını başlatmak için, aşağıdaki bilgileri sağlayarak [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread)'in ikinci aşırı yüklemesini çağırın:

- İçinden türettiğiniz sınıfın [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) `CWinThread` .

- Seçim İstenen öncelik düzeyi. Varsayılan değer normal önceliktir. Kullanılabilir öncelik düzeyleri hakkında daha fazla bilgi için Windows SDK [SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) bölümüne bakın.

- Seçim İş parçacığı için istenen yığın boyutu. Varsayılan değer, oluşturma iş parçacığıyla aynı boyut yığınıdır.

- Seçim İş parçacığının askıya alınma durumunda oluşturulmasını istiyorsanız CREATE_SUSPENDED. Varsayılan değer 0 ' dır veya iş parçacığını normal olarak başlatır.

- Seçim İstenen güvenlik öznitelikleri. Varsayılan, üst iş parçacığıyla aynı erişimdir. Bu güvenlik bilgilerinin biçimi hakkında daha fazla bilgi için Windows SDK [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bakın.

`AfxBeginThread` İşin çoğunu sizin için yapar. Sınıfınıza yeni bir nesne oluşturur, bunu sağladığınız bilgilerle başlatır ve iş parçacığını yürütmeye başlamak için [CWinThread:: CreateThread](../mfc/reference/cwinthread-class.md#createthread) öğesini çağırır. Tüm nesnelerin düzgün şekilde serbest bırakıldığından emin olmak için, oluşturma yordamının tamamında denetimler yapılır

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Çoklu iş parçacığı: Iş parçacıklarını sonlandırma](multithreading-terminating-threads.md)

- [Çoklu iş parçacığı kullanımı: çalışan Iş parçacıkları oluşturma](multithreading-creating-worker-threads.md)

- [Süreçler ve Iş parçacıkları](/windows/win32/ProcThread/processes-and-threads)

## <a name="see-also"></a>Ayrıca bkz.

[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)
