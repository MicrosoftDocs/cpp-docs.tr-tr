---
title: "Dışa aktarılan DLL işlev giriş noktaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- exporting DLLs [MFC], functions
- MFC, managing state data
- state management [MFC], exported DLLs
ms.assetid: 3268666e-d24b-44f2-80e8-7c80f73b93ca
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 28ded528d584e98b704b5f2d8e6e0a379a6a11a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="exported-dll-function-entry-points"></a>Dışa Aktarılan DLL İşlev Giriş Noktaları
DLL'den dışarı aktarılan işlevleri için kullanmak [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) DLL modülünden çağıran uygulamanın DLL'e geçerken uygun genel durumunu korumak üzere makrosu.  
  
 Çağrıldığında, bu makrosu ayarlar `pModuleState`, bir işaretçi bir `AFX_MODULE_STATE` işlevi içeren kapsamını geri kalanı etkili Modül durumu olarak modül için genel verileri içeren yapısı. Makro içeren kapsam bırakarak bağlı önceki etkili Modül durumu otomatik olarak geri.  
  
 Bu geçiş örneğini oluşturarak elde edilir bir **AFX_MODULE_STATE** yığında sınıfı. Kendi oluşturucusuna bu sınıfın geçerli modül durumunu gösteren bir işaretçi alır ve bir üye değişkeninde depolar ve ardından ayarlar `pModuleState` yeni etkili Modül durumu olarak. Kendi yıkıcı Bu sınıf, üye değişkeni etkili Modül durumu olarak depolanan işaretçi geri yükler.  
  
 Bir iletişim kutusu, DLL içinde başlatır gibi dışarı aktarılan bir işlevin varsa, aşağıdaki kodu işlevi başlangıcına eklemeniz gerekir:  
  
 [!code-cpp[NVC_MFCConnectionPoints#6](../mfc/codesnippet/cpp/exported-dll-function-entry-points_1.cpp)]  
  
 Bu döndürülen durumuyla geçerli modül durumunu değiştirir [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) geçerli kapsam sonuna kadar.  
  
 DLL'leri kaynaklarında sorunları varsa gerçekleşeceği `AFX_MANAGE_STATE` makrosu kullanılmaz. Varsayılan olarak, MFC kaynak şablonu yüklemek için ana uygulama kaynak tanıtıcısı kullanır. Bu şablon, aslında DLL'de depolanır. MFC'nin Modül durumu bilgilerini tarafından geçti değil, kök nedeni `AFX_MANAGE_STATE` makrosu. Kaynak tanıtıcısı MFC'nin modülü durumundan kurtarıldı. Modül durumu geçiş değil, kullanılacak yanlış kaynağı tanıtıcısı neden olur.  
  
 `AFX_MANAGE_STATE`Her işlevi dll yerleştirin gerekmez. Örneğin, `InitInstance` uygulamayı olmadan MFC kodu tarafından çağrılan `AFX_MANAGE_STATE` MFC modül durumu önce otomatik olarak kayar çünkü `InitInstance` ve ardından geri sonra anahtarları `InitInstance` döndürür. Aynı tüm ileti eşleme işleyiciler için geçerlidir. Normal MFC DLL'leri gerçekte herhangi ileti yönlendirme önce Modül durumu otomatik olarak geçer özel ana pencere yordamı vardır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Modüllerinin Durum Verisini Yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)

