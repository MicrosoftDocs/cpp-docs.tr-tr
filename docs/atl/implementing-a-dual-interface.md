---
title: Çift Arabirim (ATL) Uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- IDispatchImpl class, implementing dual interfaces
- dual interfaces, implementing
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
ms.openlocfilehash: a85597adad045bee3edb5cc3ed63c72a22fa08fe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319461"
---
# <a name="implementing-a-dual-interface"></a>Çift Arabirim Uygulama

Çift arabirimdeki `IDispatch` yöntemlerin varsayılan olarak uygulanmasını sağlayan [IDispatchImpl](../atl/reference/idispatchimpl-class.md) sınıfını kullanarak bir çift arabirim uygulayabilirsiniz. Daha fazla bilgi için Bkz. [IDispatch Arabirimi Uygulama.](/previous-versions/windows/desktop/automat/implementing-the-idispatch-interface)

Bu sınıfı kullanmak için:

- Çift arabiriminizi bir tür kitaplığında tanımlayın.

- Sınıfınızı uzmanlık özelliğinden türetin `IDispatchImpl` (şablon bağımsız değişkenleri olarak arabirim ve tür kitaplığı hakkında bilgi aktarın).

- Çift arabirimi ortaya çıkarmak için COM haritasına bir `QueryInterface`giriş (veya giriş) ekleyin.

- Sınıfınızdaki arabirimin vtable bölümünü uygulayın.

- Arabirim tanımını içeren tür kitaplığı çalışma zamanında nesneleriniz için kullanılabilir olduğundan emin olun.

## <a name="atl-simple-object-wizard"></a>ATL Basit Nesne Sihirbazı

Bunu uygulamak için yeni bir arabirim ve yeni bir sınıf oluşturmak istiyorsanız, [ATL Sınıf Ekle iletişim kutusunu](../ide/add-class-dialog-box.md)ve ardından [ATL Basit Nesne Sihirbazı'nı](../atl/reference/atl-simple-object-wizard.md)kullanabilirsiniz.

## <a name="implement-interface-wizard"></a>Arabirim Uygulama Sihirbazı

Varolan bir arabiriminiz varsa, varolan bir sınıfa gerekli taban sınıf, COM eşleme girişleri ve iskelet yöntemi uygulamalarını eklemek için [Arabirim](../atl/reference/adding-a-new-interface-in-an-atl-project.md) Sihirbazı'nı kullanabilirsiniz.

> [!NOTE]
> Oluşturulan taban sınıfı, tür kitaplığın büyük ve küçük sürüm numaralarının taban sınıfınıza `IDispatchImpl` şablon bağımsız değişkenler olarak geçirilmesi için ayarlamanız gerekebilir. Arabirim Uygula Sihirbazı, tür kitaplığı sürüm numarasını sizin için denetlemez.

## <a name="implementing-idispatch"></a>IDispatch'in uygulanması

Karşılık gelen `IDispatchImpl` bir ikili arabirimi açıklayan bir tür kitaplığınız olduğu sürece, com haritasında uygun girişi [(COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) veya [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid) makroyu kullanarak) belirterek bir dispinterface uygulamasını sağlamak için bir taban sınıf kullanabilirsiniz. Örneğin, `IDispatch` arabirimi bu şekilde uygulamak oldukça yaygındır. ATL Basit Nesne Sihirbazı ve Uygulama Arabirimi `IDispatch` Sihirbazı her ikisi de bu şekilde uygulamak niyetinde olduğunu varsayalım, böylece haritaya uygun girişi eklersiniz.

> [!NOTE]
> ATL, uyumlu bir ikili arabirim tanımını içeren bir tür kitaplığı gerektirmeden dispinterfaces uygulamanıza yardımcı olmak için [IDispEventImpl](../atl/reference/idispeventimpl-class.md) ve [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) sınıfları sunar.

## <a name="see-also"></a>Ayrıca bkz.

[Çift Arayüzler ve ATL](../atl/dual-interfaces-and-atl.md)
