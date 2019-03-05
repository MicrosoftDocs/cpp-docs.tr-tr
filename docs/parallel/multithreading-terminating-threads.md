---
title: 'Çoklu iş parçacığı kullanımı: MFC içinde iş parçacıklarını sonlandırma'
ms.date: 08/27/2018
f1_keywords:
- CREATE_SUSPENDED
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
ms.openlocfilehash: dd11f5db646e172d7ea2c2cc646841249d95ef31
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57303637"
---
# <a name="multithreading-terminating-threads-in-mfc"></a>Çoklu iş parçacığı kullanımı: MFC içinde iş parçacıklarını sonlandırma

İki durum iş parçacığının sonlandırılmasına neden olur: denetleyen işlev çıkar veya iş parçacığının tamamlanmaya kadar çalışmasına izin verilmez. Bir sözcük işlemcisi arka plan yazdırması için iş parçacığı kullandıysanız, başarıyla tamamlanmış yazdırma denetleyen işlev normal olarak sonlanırdı. Ancak kullanıcı yazdırmayı iptal etmek isterse, arka plan yazdırma iş parçacığının önce sonlandırılması gerekir. Bu konu, hem her durumun nasıl uygulanacağını hem de sonlandırıldıktan sonra bir iş parçacığı çıkış kodunu almak nasıl açıklar.

- [Normal iş parçacığı sonlandırma](#_core_normal_thread_termination)

- [Erken iş parçacığı sonlandırma](#_core_premature_thread_termination)

- [Bir iş parçacığı çıkış kodunu alma](#_core_retrieving_the_exit_code_of_a_thread)

##  <a name="_core_normal_thread_termination"></a> Normal iş parçacığı sonlandırma

Bir çalışan iş parçacığı için normal iş parçacığının sonlandırılması basittir: Denetleyen işlevden çıkın ve sonlandırma nedenini belirten bir değer döndürür. Kullanabilirsiniz [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) işlevi veya **dönüş** deyimi. Genellikle, 0 başarılı tamamlamayı belirtir, ancak size bağlıdır.

Bir kullanıcı arabirimi iş parçacığı için işlem basittir: kullanıcı arabirimi iş parçacığı içinde çağırmanıza [PostQuitMessage](/windows/desktop/api/winuser/nf-winuser-postquitmessage) Windows SDK. Tek parametre, `PostQuitMessage` alır, iş parçacığının çıkış kodudur. Çalışan iş parçacıkları için 0 genellikle başarılı tamamlamayı belirtir.

##  <a name="_core_premature_thread_termination"></a> Erken iş parçacığı sonlandırma

Bir iş parçacığı erken sonlandırma basittir: Çağrı [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) gelen iş parçacığı içinden. İstenen çıkış kodunu tek parametre olarak geçirirsiniz. Bu iş parçacığının yürütülmesini durdurur, iş parçacığının yığınını kaldırır, iş parçacığına bağlı olan bütün DLL'leri ayırır ve bellekten iş parçacığı nesnesini siler.

`AfxEndThread` Sonlandırılacak olan iş parçacığının içinden çağrılmalıdır. Bir iş parçacığı başka bir iş parçacığından sonlandırmak isterseniz, iki iş parçacığı arasında iletişim yöntemi ayarlamanız gerekir.

##  <a name="_core_retrieving_the_exit_code_of_a_thread"></a> Bir iş parçacığı çıkış kodunu alma

Çalışan ya da kullanıcı arabirimi iş parçacığı çıkış kodunu almak için arama [GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread) işlevi. Bu işlev hakkında daha fazla bilgi için Windows SDK'sı bakın. Bu işlev için iş parçacığı tanıtıcısını alır (depolanan `m_hThread` veri üyesi `CWinThread` nesneleri) ve bir DWORD adresidir.

İş parçacığı hala etkinse, `GetExitCodeThread` STILL_ACTIVE yerleştirir sağlanan DWORD adresi; Aksi takdirde, çıkış kodu bu adreste yerleştirilir.

Çıkış kodunu alma [CWinThread](../mfc/reference/cwinthread-class.md) nesneleri fazladan bir adım alır. Varsayılan olarak, bir `CWinThread` iş parçacığı sonlandırıldığında, iş parçacığı nesnesi silinir. Bu erişemeyeceğiniz anlamına gelir `m_hThread` veri üyesi olduğundan `CWinThread` nesnesi artık yok. Bu durumu önlemek için aşağıdakilerden birini yapın:

- Ayarlama `m_bAutoDelete` veri üyesi false. Böylece `CWinThread` iş parçacığı sonlandırıldıktan sonra varlığını sürdürmesi için nesne. Daha sonra erişebileceğiniz `m_hThread` iş parçacığı sonlandırıldıktan sonra veri üyesi. Bu yöntemi kullanırsanız, ancak, yok etmek sizin sorumluluğunuzdadır `CWinThread` nesnesini framework otomatik olarak bunu sizin için silinmesine neden olmaz. Tercih edilen yöntem budur.

- İş parçacıkları işlemesini ayrı ayrı Store. İş parçacığı oluşturulduktan sonra kopyalayın, `m_hThread` veri üyesi (kullanarak `::DuplicateHandle`) başka bir değişkene ve değişken üzerinden erişim. Bu şekilde nesne otomatik olarak sonlandırma oluşur ve iş parçacığının neden bunu hala öğrenebilirsiniz silinir. Tanıtıcı çoğaltabilirsiniz önce iş parçacığının sonlanmamasına dikkat edin. Bunu yapmak için en güvenli yolu için CREATE_SUSPENDED geçirmektir [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), işlemeyi saklamak ve ardından çağırarak iş parçacığını devam [ResumeThread](../mfc/reference/cwinthread-class.md#resumethread).

Nedenini belirlemek her iki yöntem sağlar bir `CWinThread` nesne sonlandırıldı.

## <a name="see-also"></a>Ayrıca bkz.

[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)<br/>
[_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)<br/>
[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)<br/>
[ExitThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-exitthread)
