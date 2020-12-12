---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: Yöntemler'
title: 'MFC ActiveX Denetimleri: Yöntemler'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
ms.assetid: e20271de-6ffa-4ba0-848b-bafe6c9e510c
ms.openlocfilehash: 27e56653e8a3cf3ebd7ab182b633a1c3ba0b99b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236938"
---
# <a name="mfc-activex-controls-methods"></a>MFC ActiveX Denetimleri: Yöntemler

Bir ActiveX denetimi, kendisiyle Denetim kapsayıcısı arasında iletişim kurmak için olaylar harekete geçirilir. Kapsayıcı Ayrıca Yöntemler ve özellikler aracılığıyla bir denetimle iletişim kurabilir. Yöntemler de işlevleri olarak adlandırılır.

Yöntemler ve özellikler, Otomasyon istemcileri ve ActiveX denetim kapsayıcıları gibi diğer uygulamalar tarafından kullanılmak üzere aktarılmış bir arabirim sağlar. ActiveX denetimi özellikleri hakkında daha fazla bilgi için [MFC ActiveX denetimleri: Özellikler](mfc-activex-controls-properties.md)makalesine bakın.

Yöntemler, bir C++ sınıfının üye işlevleri için kullanımda ve amaca benzer. Denetiminizin uygulayabileceğiniz iki tür yöntem vardır: stok ve özel. Hisse senedi olaylarına benzer şekilde, stok yöntemleri de [Coelcontrol](reference/colecontrol-class.md) 'un bir uygulama sağladığı yöntemlerdir. Stok yöntemleri hakkında daha fazla bilgi için [MFC ActiveX denetimleri: stok yöntemleri ekleme](mfc-activex-controls-adding-stock-methods.md)makalesine bakın. Geliştirici tarafından tanımlanan özel yöntemler, denetimin ek özelleştirmesine izin verir. Daha fazla bilgi için [MFC ActiveX denetimleri: özel yöntemler ekleme](mfc-activex-controls-adding-custom-methods.md)makalesine bakın.

Microsoft Foundation Class Kitaplığı (MFC), denetiminizin stok ve özel yöntemleri desteklemesini sağlayan bir mekanizma uygular. Birinci bölüm bir sınıftır `COleControl` . Öğesinden türetilmiş `CWnd` , `COleControl` üye Işlevleri tüm ActiveX denetimlerinde ortak olan stok yöntemlerini destekler. Bu mekanizmanın ikinci bölümü, dağıtım eşlemedir. Dağıtım eşlemesi bir ileti eşlemesine benzer; Ancak, bir işlevi Windows ileti KIMLIĞI ile eşleştirmek yerine, bir dağıtım eşlemesi sanal üye işlevlerini IDispatch KIMLIKLERINE eşler.

Bir denetimin çeşitli yöntemleri düzgün şekilde desteklemesi için, sınıfının bir dağıtım eşlemesi bildirmesi gerekir. Bu, denetim sınıfı üst bilgisinde bulunan aşağıdaki kod satırıyla gerçekleştirilir (. H) dosyası:

[!code-cpp[NVC_MFC_AxUI#13](codesnippet/cpp/mfc-activex-controls-methods_1.h)]

Dağıtım eşlemesinin asıl amacı, bir dış çağıran (kapsayıcı gibi) tarafından kullanılan yöntem adları ve yöntemleri uygulayan denetimin sınıfının üye işlevleri arasında ilişki kurmak için kullanılır. Dağıtım eşlemesi bildirildiğinde, denetimin uygulamasında tanımlanması gerekir (. CPP) dosyası. Aşağıdaki kod satırları dağıtım haritasını tanımlar:

[!code-cpp[NVC_MFC_AxUI#14](codesnippet/cpp/mfc-activex-controls-methods_2.cpp)]
[!code-cpp[NVC_MFC_AxUI#15](codesnippet/cpp/mfc-activex-controls-methods_3.cpp)]

Projeyi oluşturmak için [MFC ActiveX Denetim Sihirbazı 'nı](reference/mfc-activex-control-wizard.md) kullandıysanız, bu satırlar otomatik olarak eklenir. MFC ActiveX denetimi Sihirbazı kullanılmıyorsa, bu satırları el ile eklemeniz gerekir.

Aşağıdaki makalelerde Yöntemler ayrıntılı olarak ele alınmaktadır:

- [MFC ActiveX denetimleri: stok yöntemleri ekleme](mfc-activex-controls-adding-stock-methods.md)

- [MFC ActiveX denetimleri: özel yöntemler ekleme](mfc-activex-controls-adding-custom-methods.md)

- [MFC ActiveX denetimleri: bir yöntemden hata kodları döndürme](mfc-activex-controls-returning-error-codes-from-a-method.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)
