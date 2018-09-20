---
title: 'MFC ActiveX denetimleri: Yöntemler | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
ms.assetid: e20271de-6ffa-4ba0-848b-bafe6c9e510c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93a8d3f9840afd88a9ce0ae7cbaf661babc13647
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406054"
---
# <a name="mfc-activex-controls-methods"></a>MFC ActiveX Denetimleri: Yöntemler

ActiveX denetimi kendisi ve denetim kapsayıcısı arasında iletişim kurmak için olayları tetikler. Bir kapsayıcı da yöntemleri ve özellikleri kullanarak bir denetimi ile iletişim kurabilir. Yöntemler, İşlevler olarak da adlandırılır.

Dışarı aktarılan arabirimin yöntemlerini ve özelliklerini kullanmak için Otomasyon istemcileri ve ActiveX denetim kapsayıcıları gibi diğer uygulamalar tarafından sağlar. ActiveX denetimi özellikleri hakkında daha fazla bilgi için bkz [MFC ActiveX denetimleri: Özellikler](../mfc/mfc-activex-controls-properties.md).

Yöntemleri kullanın ve amaçlı C++ sınıf üye işlevleri için benzerdir. Denetiminiz uygulayabilirsiniz yöntemleri iki tür vardır: stok ve özel. Bu yöntem, olayları stok yöntemleri hisse senedi için benzer [COleControl](../mfc/reference/colecontrol-class.md) bir uygulamasını sağlar. Stok yöntemleri hakkında daha fazla bilgi için bkz [MFC ActiveX denetimleri: stok yöntemler ekleme](../mfc/mfc-activex-controls-adding-stock-methods.md). Geliştirici tarafından tanımlanan özel yöntemler denetimin ek özelleştirmeye izin verir. Daha fazla bilgi için bkz [MFC ActiveX denetimleri: özel yöntemler ekleme](../mfc/mfc-activex-controls-adding-custom-methods.md).

Microsoft Foundation Class Kitaplığı'nı (MFC), stok ve özel yöntemler desteklemek, denetim sağlayan bir mekanizma uygular. İlk bölümü sınıftır `COleControl`. Türetilmiş `CWnd`, `COleControl` üye işlevlerini destekleyen tüm ActiveX denetimleri için ortak olan stok yöntemler. Bu mekanizma ikinci bölümü, gönderme haritasıdır. Dağıtım eşlemesi için ileti eşlemesi benzer. Ancak, bir Windows ileti kimliği için bir işlev eşlemesi yerine bir dağıtım eşlemesi IDispatch KİMLİKLERİ için bir sanal üye işlev eşler.

Çeşitli yöntemler düzgün bir şekilde desteklemek bir denetim için bir dağıtım eşlemesi sınıfıyla bildirmeniz gerekir. Bu denetim sınıf üstbilgisinde bulunan kodu aşağıdaki satırı tarafından gerçekleştirilir (. H) dosyası:

[!code-cpp[NVC_MFC_AxUI#13](../mfc/codesnippet/cpp/mfc-activex-controls-methods_1.h)]

Dağıtım eşlemesi ana amacı (kapsayıcı gibi) bir dış arayan ve yöntemlerini uygulayan denetimin sınıf üye işlevleri tarafından kullanılan yöntem adları arasındaki ilişkiyi oluşturmaktır. Dağıtım eşlemesi bildirildikten sonra bu denetimin uygulamasında tanımlanması gerekir (. CPP) dosyası. Dağıtım eşlemesi aşağıdaki kod satırlarını tanımlayın:

[!code-cpp[NVC_MFC_AxUI#14](../mfc/codesnippet/cpp/mfc-activex-controls-methods_2.cpp)]
[!code-cpp[NVC_MFC_AxUI#15](../mfc/codesnippet/cpp/mfc-activex-controls-methods_3.cpp)]

Kullandıysanız [MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md) projeyi oluşturmak için bu satırları otomatik olarak eklendi. MFC ActiveX Denetim Sihirbazı'nı kullanılmamışsa bu satırlar el ile eklemeniz gerekir.

Aşağıdaki makaleler ayrıntılı yöntemler açıklanmaktadır:

- [MFC ActiveX Denetimleri: Stok Yöntemler Ekleme](../mfc/mfc-activex-controls-adding-stock-methods.md)

- [MFC ActiveX Denetimleri: Özel Yöntemler Ekleme](../mfc/mfc-activex-controls-adding-custom-methods.md)

- [MFC ActiveX Denetimleri: Bir Metottan Hata Kodları Döndürme](../mfc/mfc-activex-controls-returning-error-codes-from-a-method.md)

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

