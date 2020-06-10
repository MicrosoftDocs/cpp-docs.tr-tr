---
title: Dışa Aktarılan DLL İşlev Giriş Noktaları
ms.date: 11/04/2016
helpviewer_keywords:
- exporting DLLs [MFC], functions
- MFC, managing state data
- state management [MFC], exported DLLs
ms.assetid: 3268666e-d24b-44f2-80e8-7c80f73b93ca
ms.openlocfilehash: c521cad666864c728fd871b460cf0c92b815e414
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622637"
---
# <a name="exported-dll-function-entry-points"></a>Dışa Aktarılan DLL İşlev Giriş Noktaları

DLL 'nin içe aktarılmış işlevleri için, DLL modülünden çağıran uygulamanın DLL 'sine geçiş yaparken doğru genel durumu korumak için [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) makrosunu kullanın.

Çağrıldığında, bu makro, söz konusu `pModuleState` `AFX_MODULE_STATE` işlevin bulunduğu kapsamın geri kalanı için geçerli modül durumu olarak, modülün genel verilerini içeren bir yapıya yönelik bir işaretçi olarak ayarlanır. Makroyu içeren kapsamdan ayrıldıktan sonra, önceki etkin modül durumu otomatik olarak geri yüklenir.

Bu geçiş, yığındaki bir sınıfın bir örneği oluşturularak elde edilir `AFX_MODULE_STATE` . Bu sınıf, yapıcısında geçerli modül durumuna bir işaretçi edinir ve bir üye değişkeninde depolar ve sonra `pModuleState` yeni etkin modül durumu olarak ayarlar. Bu sınıf, yıkıcısında, etkin modül durumu olarak kendi üye değişkeninde depolanan işaretçiyi geri yükler.

DLL 'inizde bir iletişim kutusu Başlatan gibi bir içe aktarılmış işleviniz varsa, işlevin başlangıcına aşağıdaki kodu eklemeniz gerekir:

[!code-cpp[NVC_MFCConnectionPoints#6](codesnippet/cpp/exported-dll-function-entry-points_1.cpp)]

Bu, geçerli modülün durumunu geçerli kapsamın sonuna kadar [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) öğesinden döndürülen durum ile değiştirir.

Makrolar kullanılmıyorsa, dll 'Lerdeki kaynaklarla ilgili sorunlar oluşur `AFX_MANAGE_STATE` . Varsayılan olarak, MFC kaynak şablonunu yüklemek için ana uygulamanın kaynak tanıtıcısını kullanır. Bu şablon aslında DLL 'de depolanır. Kök nedeni, MFC 'nin modül durumu bilgisinin makro tarafından geçmemelidir `AFX_MANAGE_STATE` . Kaynak tanıtıcısı, MFC 'nin modül durumundan kurtarıldı. Modül durumunun değiştirilmemesi yanlış kaynak tanıtıcısının kullanılmasına neden olur.

`AFX_MANAGE_STATE`DLL içindeki her işleve yerleştirilmeye gerek yoktur. Örneğin, `InitInstance` `AFX_MANAGE_STATE` MFC, modül durumunu önce otomatik olarak kaydığı `InitInstance` ve ardından döndürmeden sonra geri anahtarlamadığından, uygulamada MFC kodu tarafından çağrılabilir `InitInstance` . Tüm ileti eşleme işleyicileri için de aynı değer geçerlidir. Normal MFC DLL 'Lerinin aslında herhangi bir iletiyi yönlendirmeden önce modül durumunu otomatik olarak yönlendiren özel bir ana pencere prosedürü vardır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC modüllerinin durum verilerini yönetme](managing-the-state-data-of-mfc-modules.md)
