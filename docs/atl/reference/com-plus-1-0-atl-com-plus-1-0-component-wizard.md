---
description: 'Daha fazla bilgi edinin: COM+ 1,0, ATL COM+ 1,0 Bileşen Sihirbazı'
title: COM+ 1.0, ATL COM+ 1.0 Bileşeni Sihirbazı
ms.date: 05/09/2019
f1_keywords:
- vc.codewiz.class.atl.mts.options
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
ms.openlocfilehash: 581a258fc2702465fea40590430080bb6b9fcd66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141303"
---
# <a name="com-10-atl-com-10-component-wizard"></a>COM+ 1.0, ATL COM+ 1.0 Bileşeni Sihirbazı

::: moniker range="msvc-160"

Bu sihirbaz, Visual Studio 2019 ve sonrasında kullanılamaz.

::: moniker-end

::: moniker range="<=msvc-150"

Arabirim türünü ve desteklenecek ek arabirimleri belirtmek için ATL COM+ 1,0 Bileşen Sihirbazı 'nın bu sayfasını kullanın.

ATL projeleri ve ATL COM sınıfları hakkında daha fazla bilgi için bkz. [atl com Masaüstü bileşenleri](../../atl/atl-com-desktop-components.md).

- **Arabirim**

   Nesnenin desteklediği arabirimin türünü gösterir. Varsayılan olarak, nesnesi bir çift arabirimi destekler.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**İkili**|Nesnenin çift arabirimi desteklediğini belirtir (vtable, özel arabirim işlevlerine ve geç bağlama `IDispatch` yöntemlerine sahiptir). Hem COM istemcilerinin hem de Otomasyon denetleyicilerinin nesneye erişmesine izin verir.|
   |**Özel**|Nesnenin özel arabirimi desteklediğini belirtir (vtable 'ın özel arabirim işlevleri vardır). Özel bir arabirim, özellikle işlem sınırları genelinde bir çift arabirimden daha hızlı olabilir.<br /><br /> - **Otomasyon uyumlu** Özel arabirime Otomasyon desteği ekler. Öznitelikli projeler için, coclass 'ta **oleautomation** özniteliğini ayarlar.|

- **Kuyruğa atılabilir**

   İstemcilerin bu bileşeni ileti kuyruklarını kullanarak zaman uyumsuz olarak çağırabileceğini belirtir. Öznitelikli makro özel (TLBATTR_QUEUEABLE, 0) bileşenini. h dosyasına (öznitelikli projeler) veya. IDL dosyasına (öznitelikli projeler) ekler.

- **Destek**

   Hata işleme ve nesne denetimi için ek desteği gösterir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Iupporterrorınfo**|, Nesnenin istemciye hata bilgilerini döndürebilmesi için [ıupporterrorınfo](../../atl/reference/isupporterrorinfoimpl-class.md) arabirimi için destek oluşturur.|
   |**IObjectControl**|Nesnenizin üç [IObjectControl](/windows/win32/api/comsvcs/nn-comsvcs-iobjectcontrol) yöntemine erişmesini sağlar: [Etkinleştir](/windows/win32/api/comsvcs/nf-comsvcs-iobjectcontrol-activate), [Canbehavuza](/windows/win32/api/comsvcs/nf-comsvcs-iobjectcontrol-canbepooled)al ve [devre dışı bırak](/windows/win32/api/comsvcs/nf-comsvcs-iobjectcontrol-deactivate).|
   |**IObjectConstruct**|Diğer yöntemlerden veya nesnelerden parametreleri geçirmeyi yönetmek için [ıobjectyapý](/windows/win32/api/comsvcs/nn-comsvcs-iobjectconstruct) arabirimine yönelik destek oluşturur.|

- **İşlem**

   Nesnenin işlemleri desteklediğini gösterir. . IDL dosyasındaki (öznitelikli projeler) mtxattr. h dosyasını içerir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Desteklenir**|Nesne,. h dosyasına (öznitelikli projeler) veya. IDL dosyasına (öznitelik atanmış olmayan projeler) bileşen özniteliği makrosunu (TLBATTR_TRANS_SUPPORTED, 0) ekleyerek bir işlem akışının hiçbir şekilde kök olduğunu belirtir.|
   |**Gerekli**|Nesnesinin,. h dosyasına (öznitelikli projeler) veya. IDL dosyasına (öznitelik atanmış olmayan projeler) bileşen özniteliği makrosunu (TLBATTR_TRANS_REQUIRED, 0) ekleyerek bir işlem akışının kökü olabileceğini veya olabileceğini belirtir.|
   |**Desteklenmiyor**|Nesnenin işlemleri dışladığı belirtir. Bileşen özniteliği makrosu özel (TLBATTR_TRANS_NOTSUPP, 0). h dosyasına (öznitelikli projeler) veya. IDL dosyasına (öznitelikli projeler) ekler.|
   |**Yeni gerektirir**|Nesne. h dosyasına (TLBATTR_TRANS_REQNEW, 0) bileşen özniteliği makrosunu (öznitelikli projeler) veya. IDL dosyasına (öznitelik atanmış olmayan projeler) ekleyerek nesnenin her zaman bir işlem akışının kök olduğunu belirtir.|

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM+ 1.0 Bileşeni Sihirbazı](../../atl/reference/atl-com-plus-1-0-component-wizard.md)<br/>
[ATL COM+ 1,0 bileşeni](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)
