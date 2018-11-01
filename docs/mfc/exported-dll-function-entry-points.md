---
title: Dışa Aktarılan DLL İşlev Giriş Noktaları
ms.date: 11/04/2016
helpviewer_keywords:
- exporting DLLs [MFC], functions
- MFC, managing state data
- state management [MFC], exported DLLs
ms.assetid: 3268666e-d24b-44f2-80e8-7c80f73b93ca
ms.openlocfilehash: 8b84209833fee42ec8ebdd1fdea7a9229decad9d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463333"
---
# <a name="exported-dll-function-entry-points"></a>Dışa Aktarılan DLL İşlev Giriş Noktaları

Bir DLL'nin dışarı aktarılan işlevler için kullanmak [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) DLL modülünden çağıran uygulamanın DLL'ye geçiş yaparken uygun genel durumunu korumak üzere makrosu.

Çağrıldığında, bu makroyu ayarlar `pModuleState`, işaretçi bir `AFX_MODULE_STATE` işlevi içeren kapsamını geri kalanı için geçerli Modül durumu genel veri modülü için içeren yapısı. Makro içeren kapsamı ayrıldıktan sonra önceki etkili Modül durumu otomatik olarak geri.

Bu geçiş örneği oluşturularak elde edilir bir `AFX_MODULE_STATE` yığında sınıfı. Oluşturucusuna, bu sınıf geçerli Modül durumu için bir işaretçi alır ve bir üye değişkeni depolar ve ardından ayarlar `pModuleState` yeni etkin Modül durumu olarak. Yok edici, bu sınıfın üye değişkeni etkili Modül durumu olarak depolanan işaretçi geri yükler.

Dışarı aktarılan bir işlevin bir DLL dosyanız bir iletişim kutusunda başlatan gibi varsa işlevin başlangıcına aşağıdaki kodu ekleyin gerekir:

[!code-cpp[NVC_MFCConnectionPoints#6](../mfc/codesnippet/cpp/exported-dll-function-entry-points_1.cpp)]

Bu geçerli bir modül durumunu döndürüldüğü durumu ile değiştirir [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) geçerli kapsamdaki sonuna kadar.

DLL'lerde kaynakları ile ilgili sorunlar varsa gerçekleşir `AFX_MANAGE_STATE` makrosu kullanılmaz. Varsayılan olarak, kaynak şablonu yüklemek için ana uygulama kaynak tanıtıcısı MFC kullanır. Bu şablon, aslında DLL içinde depolanır. MFC modül durumu bilgilerini tarafından kullanılamayacağı değil, kök nedeni `AFX_MANAGE_STATE` makrosu. MFC modül durumu kaynağı tanıtıcısı kurtarılır. Modül durumu geçiş değil, kullanılacak yanlış kaynak tanıtıcısı neden olur.

`AFX_MANAGE_STATE` Her işlev DLL yerleştirmenin gerekmez. Örneğin, `InitInstance` olmadan uygulamayı MFC kod tarafından çağrılabilir `AFX_MANAGE_STATE` MFC modül durumu önce otomatik olarak kayar çünkü `InitInstance` ve ardından geri sonra anahtarları `InitInstance` döndürür. Aynı tüm ileti eşleme işleyiciler için de geçerlidir. Normal MFC DLL'leri gerçekte herhangi bir ileti yönlendirme önce Modül durumu otomatik olarak geçer bir özel ana pencere yordamı vardır.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Modüllerinin Durum Verisini Yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)

