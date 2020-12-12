---
description: "Daha fazla bilgi edinin: çoklu iş parçacığı: MFC 'de Iş parçacıklarını sonlandırma"
title: "Çoklu iş parçacığı: MFC 'de Iş parçacıklarını sonlandırma"
ms.date: 08/27/2018
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
ms.openlocfilehash: dc353bc0edf14d718ee11e140fca11e4c0545588
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149883"
---
# <a name="multithreading-terminating-threads-in-mfc"></a>Çoklu iş parçacığı: MFC 'de Iş parçacıklarını sonlandırma

Bir iş parçacığının sonlandırılmasına iki normal durum neden olur: denetim işlevi çıkıyor veya iş parçacığının tamamlamaya çalışmasına izin verilmiyor. Bir sözcük işlemcisi arka planda yazdırma için bir iş parçacığı kullanıyorsa, yazdırma başarıyla tamamlanırsa denetim işlevi normal olarak sonlandırılır. Ancak Kullanıcı yazdırmayı iptal etmek isterse, arka plan yazdırma iş parçacığının erken sonlandırılması gerekir. Bu konu, her durumun nasıl uygulanacağını ve sonlandıktan sonra bir iş parçacığının çıkış kodunu almayı açıklamaktadır.

- [Normal Iş parçacığı sonlandırma](#_core_normal_thread_termination)

- [Erken Iş parçacığı sonlandırma](#_core_premature_thread_termination)

- [Bir Iş parçacığının çıkış kodunu alma](#_core_retrieving_the_exit_code_of_a_thread)

## <a name="normal-thread-termination"></a><a name="_core_normal_thread_termination"></a> Normal Iş parçacığı sonlandırma

Çalışan iş parçacığı için normal iş parçacığı sonlandırması basittir: denetim işlevinden çıkın ve sonlandırma nedenini belirten bir değer döndürün. [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) işlevini ya da bir **`return`** ifadesini kullanabilirsiniz. Genellikle 0 başarılı tamamlamayı belirtir, ancak bu kadar çok.

Kullanıcı arabirimi iş parçacığı için, işlem yalnızca basittir: Kullanıcı arabirimi iş parçacığı içinden, Windows SDK [PostQuitMessage](/windows/win32/api/winuser/nf-winuser-postquitmessage) ' ı çağırın. Alan tek parametre, `PostQuitMessage` iş parçacığının çıkış kodudur. Çalışan iş parçacıkları için 0 genellikle başarılı tamamlamayı belirtir.

## <a name="premature-thread-termination"></a><a name="_core_premature_thread_termination"></a> Erken Iş parçacığı sonlandırma

Bir iş parçacığını erken sonlandırmak neredeyse basittir: iş parçacığı içinden [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) çağrısı yapın. İstenen çıkış kodunu tek parametre olarak geçirin. Bu işlem, iş parçacığının yürütülmesini bırakır, iş parçacığının yığınını kaldırır, iş parçacığına ekli olan tüm dll 'Leri ayırır ve iş parçacığı nesnesini bellekten siler.

`AfxEndThread` Sonlandırılacak iş parçacığının içinden çağrılmalıdır. Bir iş parçacığını başka bir iş parçacığından sonlandırmak isterseniz, iki iş parçacığı arasında bir iletişim yöntemi ayarlamanız gerekir.

## <a name="retrieving-the-exit-code-of-a-thread"></a><a name="_core_retrieving_the_exit_code_of_a_thread"></a> Bir Iş parçacığının çıkış kodunu alma

Çalışan ya da Kullanıcı arabirimi iş parçacığının çıkış kodunu almak için [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread) işlevini çağırın. Bu işlev hakkında daha fazla bilgi için Windows SDK bakın. Bu işlev iş parçacığına olan tanıtıcıyı ( `m_hThread` nesnelerin veri üyesinde depolanır `CWinThread` ) ve bir DWORD adresini alır.

İş parçacığı hala etkin ise, `GetExitCodeThread` sağlanan DWORD adresine STILL_ACTIVE koyar; Aksi takdirde çıkış kodu bu adrese yerleştirilir.

[CWinThread](../mfc/reference/cwinthread-class.md) nesnelerinin çıkış kodunu almak fazladan bir adım sürer. Varsayılan olarak, bir `CWinThread` iş parçacığı sonlandırıldığında iş parçacığı nesnesi silinir. Bu, `m_hThread` nesne artık mevcut olmadığından veri üyesine erişemeyeceğiniz anlamına gelir `CWinThread` . Bu durumdan kaçınmak için aşağıdakilerden birini yapın:

- `m_bAutoDelete`Veri ÜYESINI false olarak ayarlayın. Bu, `CWinThread` iş parçacığı sonlandırıldıktan sonra nesnenin varlığını sürdürmesini sağlar. Daha sonra `m_hThread` iş parçacığı sonlandırıldıktan sonra veri üyesine erişebilirsiniz. Bununla birlikte, bu tekniği kullanırsanız, `CWinThread` Framework sizin için otomatik olarak silmediğinden nesnenin yok edilmesi sizin sorumluluğunuzdadır. Bu tercih edilen yöntemdir.

- İş parçacığının işleyicisini ayrı olarak depolayın. İş parçacığı oluşturulduktan sonra, `m_hThread` veri üyesini (kullanarak `::DuplicateHandle` ) başka bir değişkene kopyalayın ve bu değişken aracılığıyla erişin. Bu şekilde, sonlandırma gerçekleştiğinde nesne otomatik olarak silinir ve iş parçacığının neden sonlandırıldığını yine de öğrenebilirsiniz. Tanıtıcıyı çoğaltmak için iş parçacığının sonlandırılmadığından dikkatli olun. Bunu yapmanın en güvenli yolu, CREATE_SUSPENDED [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread)'e geçirmektir, tanıtıcıyı depolar ve sonra [ResumeThread](../mfc/reference/cwinthread-class.md#resumethread)'i çağırarak iş parçacığını sürdürür.

Her iki yöntem de bir `CWinThread` nesnenin neden sonlandırıldığını belirlemenizi sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[C++ ve MCF ile Çoklu İş Parçacığı Kullanımı](multithreading-with-cpp-and-mfc.md)<br/>
[_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)<br/>
[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)<br/>
[ExitThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread)
