---
title: "MFC ActiveX denetimleri: Yöntemler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: MFC ActiveX controls [MFC], methods
ms.assetid: e20271de-6ffa-4ba0-848b-bafe6c9e510c
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f1c0fe2f5e54205c3e9c82ebf1d9cb40504e5023
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-activex-controls-methods"></a>MFC ActiveX Denetimleri: Yöntemler
ActiveX denetimi kendisi ve kendi denetimi kapsayıcısı arasında iletişim kurmak için olay tetikler. Bir kapsayıcı ayrıca yöntemleri ve özellikleri yoluyla denetimi ile iletişim kurabilir. Yöntemleri işlevleri de denir.  
  
 Yöntemleri ve özellikleri dışarı aktarılan bir arabirim Otomasyon istemcileri ve ActiveX denetimi kapsayıcıları gibi diğer uygulamalar tarafından kullanılmak üzere sağlar. ActiveX denetimi özellikleri hakkında daha fazla bilgi için bkz: [MFC ActiveX denetimleri: Özellikler](../mfc/mfc-activex-controls-properties.md).  
  
 Yöntemleri kullanmak ve amacı C++ sınıfının üye fonksiyonları benzerdir. İki tür denetiminizi uygulayabilirsiniz yöntemi vardır: stok ve özel. Bu yöntemler, olayları hisse senedi, yöntemleri hisse senedi benzer [COleControl](../mfc/reference/colecontrol-class.md) bir uygulamasını sağlar. Stok yöntemleri hakkında daha fazla bilgi için bkz: [MFC ActiveX denetimleri: stok yöntemler ekleme](../mfc/mfc-activex-controls-adding-stock-methods.md). Geliştirici tarafından tanımlanan özel yöntemler denetiminin ek özelleştirmeye izin verir. Daha fazla bilgi için bkz: [MFC ActiveX denetimleri: özel yöntemler ekleme](../mfc/mfc-activex-controls-adding-custom-methods.md).  
  
 Microsoft Foundation Class Kitaplığı (MFC) stock ve özel yöntemler desteklemek, denetim sağlayan bir mekanizma uygular. İlk bölümü sınıftır `COleControl`. Türetilmiş `CWnd`, `COleControl` üye işlevleri desteklemek için tüm ActiveX denetimlerini ortak stok yöntemler. İkinci bu düzenek gönderme harita parçasıdır. Dağıtım eşlemesi için ileti eşlemesi benzer; Ancak, bir Windows ileti kimliği için bir işlev eşleme yerine bir gönderme harita IDispatch KİMLİKLERİ sanal üye işlevleri eşler.  
  
 Çeşitli yöntemlerle düzgün desteklemek bir denetim için kendi sınıfı gönderme harita bildirmeniz gerekir. Bu kod denetimi sınıfı üstbilgisinde bulunan aşağıdaki satırı tarafından gerçekleştirilir (. H) dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#13](../mfc/codesnippet/cpp/mfc-activex-controls-methods_1.h)]  
  
 Bir dış arayan (örneğin, kapsayıcı) ve yöntemleri üye işlevleri denetimin sınıfı tarafından kullanılan yöntem adları arasında ilişki kurmak için gönderme harita ana amacı budur. Gönderme harita bildirildikten sonra bu denetimin uygulamasında tanımlanması gerekiyor (. CPP) dosyası. Aşağıdaki kod satırlarını gönderme harita tanımlayın:  
  
 [!code-cpp[NVC_MFC_AxUI#14](../mfc/codesnippet/cpp/mfc-activex-controls-methods_2.cpp)]  
[!code-cpp[NVC_MFC_AxUI#15](../mfc/codesnippet/cpp/mfc-activex-controls-methods_3.cpp)]  
  
 Kullandıysanız [MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md) projesi oluşturmak için bu satırları otomatik olarak eklenen. MFC ActiveX Denetim Sihirbazı'nı kullanılmamışsa bu satırları el ile eklemeniz gerekir.  
  
 Aşağıdaki makaleler yöntemleri ayrıntılı ele alınmıştır:  
  
-   [MFC ActiveX denetimleri: Stok yöntemler ekleme](../mfc/mfc-activex-controls-adding-stock-methods.md)  
  
-   [MFC ActiveX denetimleri: Özel yöntemler ekleme](../mfc/mfc-activex-controls-adding-custom-methods.md)  
  
-   [MFC ActiveX denetimleri: Bir yöntemden hata kodları döndürme](../mfc/mfc-activex-controls-returning-error-codes-from-a-method.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)

