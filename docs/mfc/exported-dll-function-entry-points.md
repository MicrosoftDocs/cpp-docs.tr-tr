---
title: Dışa aktarılan DLL işlev giriş noktaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exporting DLLs [MFC], functions
- MFC, managing state data
- state management [MFC], exported DLLs
ms.assetid: 3268666e-d24b-44f2-80e8-7c80f73b93ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1be4c74a48f1367369582b433a2a833ceb8e1976
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343859"
---
# <a name="exported-dll-function-entry-points"></a>Dışa Aktarılan DLL İşlev Giriş Noktaları
DLL'den dışarı aktarılan işlevleri için kullanmak [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) DLL modülünden çağıran uygulamanın DLL'e geçerken uygun genel durumunu korumak üzere makrosu.  
  
 Çağrıldığında, bu makrosu ayarlar `pModuleState`, bir işaretçi bir `AFX_MODULE_STATE` işlevi içeren kapsamını geri kalanı etkili Modül durumu olarak modül için genel verileri içeren yapısı. Makro içeren kapsam bırakarak bağlı önceki etkili Modül durumu otomatik olarak geri.  
  
 Bu geçiş örneğini oluşturarak elde edilir bir **AFX_MODULE_STATE** yığında sınıfı. Kendi oluşturucusuna bu sınıfın geçerli modül durumunu gösteren bir işaretçi alır ve bir üye değişkeninde depolar ve ardından ayarlar `pModuleState` yeni etkili Modül durumu olarak. Kendi yıkıcı Bu sınıf, üye değişkeni etkili Modül durumu olarak depolanan işaretçi geri yükler.  
  
 Bir iletişim kutusu, DLL içinde başlatır gibi dışarı aktarılan bir işlevin varsa, aşağıdaki kodu işlevi başlangıcına eklemeniz gerekir:  
  
 [!code-cpp[NVC_MFCConnectionPoints#6](../mfc/codesnippet/cpp/exported-dll-function-entry-points_1.cpp)]  
  
 Bu döndürülen durumuyla geçerli modül durumunu değiştirir [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) geçerli kapsam sonuna kadar.  
  
 DLL'leri kaynaklarında sorunları varsa gerçekleşeceği `AFX_MANAGE_STATE` makrosu kullanılmaz. Varsayılan olarak, MFC kaynak şablonu yüklemek için ana uygulama kaynak tanıtıcısı kullanır. Bu şablon, aslında DLL'de depolanır. MFC'nin Modül durumu bilgilerini tarafından geçti değil, kök nedeni `AFX_MANAGE_STATE` makrosu. Kaynak tanıtıcısı MFC'nin modülü durumundan kurtarıldı. Modül durumu geçiş değil, kullanılacak yanlış kaynağı tanıtıcısı neden olur.  
  
 `AFX_MANAGE_STATE` Her işlevi dll yerleştirin gerekmez. Örneğin, `InitInstance` uygulamayı olmadan MFC kodu tarafından çağrılan `AFX_MANAGE_STATE` MFC modül durumu önce otomatik olarak kayar çünkü `InitInstance` ve ardından geri sonra anahtarları `InitInstance` döndürür. Aynı tüm ileti eşleme işleyiciler için geçerlidir. Normal MFC DLL'leri gerçekte herhangi ileti yönlendirme önce Modül durumu otomatik olarak geçer özel ana pencere yordamı vardır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Modüllerinin Durum Verisini Yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)

