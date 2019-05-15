---
title: COM + 1.0, ATL COM + 1.0 bileşeni Sihirbazı
ms.date: 05/09/2019
f1_keywords:
- vc.codewiz.class.atl.mts.options
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
ms.openlocfilehash: bff7f87fbdebbff9a1823ae8718c64be4f47a2ea
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65707448"
---
# <a name="com-10-atl-com-10-component-wizard"></a>COM + 1.0, ATL COM + 1.0 bileşeni Sihirbazı

::: moniker range="vs-2019"

Bu sihirbaz, Visual Studio 2019 bulunan ve daha yeni değil.

::: moniker-end

::: moniker range="<=vs-2017"

ATL COM + 1.0 bileşeni Sihirbazı bu sayfanın bir arabirim türüne ve ek arabirimleri desteklenecek belirtmek için kullanın.

ATL projeleri ve ATL COM sınıfları hakkında daha fazla bilgi için bkz. [ATL COM Masaüstü bileşenleri](../../atl/atl-com-desktop-components.md).

- **Arabirimi**

   Nesne destekleyen arabirim türünü belirtir. Varsayılan olarak, nesne çift arabirim destekler.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Çift**|Nesne çift arabirim desteklediğini belirtir (özel arabirim işlevi ve geç bağlama, vtable olan `IDispatch` yöntemleri). COM istemcilerinde ve Otomasyon denetleyicileri nesneye erişim sağlar.|
   |**Özel**|Nesne (özel arabirim işlevleri kendi vtable sahiptir) özel bir arabirim desteklediğini belirtir. Özel arabirim özellikle işlem sınırları arasında çift arabirim, daha hızlı olabilir.<br /><br /> - **Otomasyon uyumlu** özel Otomasyon desteği ekler. Öznitelikli projeler için ayarlar **oleautomation** coclass özniteliği.|

- **Kuyruğa atılabilir**

   İstemcilerin zaman uyumsuz ileti kuyrukları kullanarak bu bileşeni çağırabilirsiniz gösterir. Öznitelikli bileşen makrosu özel (TLBATTR_QUEUEABLE, 0) .h dosyası (öznitelikli projeler) veya .idl dosyasına (nonattributed projeler) ekler.

- **Destek**

   Hata işleme ve nesne denetimi için ek destek gösterir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**ISupportErrorInfo**|Desteği oluşturur [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) istemciye hata bilgilerini nesnenin dönebilmeniz arabirim.|
   |**IObjectControl**|Üç nesne erişiminizi sağlayan [IObjectControl](/windows/desktop/api/comsvcs/nn-comsvcs-iobjectcontrol) yöntemleri: [Etkinleştirme](/windows/desktop/api/comsvcs/nf-comsvcs-iobjectcontrol-activate), [CanBePooled](/windows/desktop/api/comsvcs/nf-comsvcs-iobjectcontrol-canbepooled), ve [devre dışı bırakma](/windows/desktop/api/comsvcs/nf-comsvcs-iobjectcontrol-deactivate).|
   |**IObjectConstruct'ı**|Desteği oluşturur [IObjectConstruct'ı](/windows/desktop/api/comsvcs/nn-comsvcs-iobjectconstruct) geçirme parametrelerinde diğer yöntemleri veya nesneleri yönetmek için arabirim.|

- **İşlem**

   Nesne işlemleri desteklediğini belirtir. Dosya mtxattr.h .idl dosyasında (nonattributed projeler) içerir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Destekleniyor**|Nesne hiçbir zaman bir işlem akışını kök bileşeni özniteliği makrosu custom(TLBATTR_TRANS_SUPPORTED,0) .h dosyası (öznitelikli projeler) veya (nonattributed projeler) .idl dosyasına ekleyerek olduğunu belirtir.|
   |**Gerekli**|Nesne olabilir veya bir işlem akışını kök bileşeni özniteliği makrosu custom(TLBATTR_TRANS_REQUIRED,0) .h dosyası (öznitelikli projeler) veya (nonattributed projeler) .idl dosyasına ekleyerek olmayabilir belirtir.|
   |**Desteklenmiyor**|Nesne işlemleri hariç belirtir. Bileşen özniteliği makrosu custom(TLBATTR_TRANS_NOTSUPP,0) .h dosyası (öznitelikli projeler) veya .idl dosyasına (nonattributed projeler) ekler.|
   |**Yeni gerektirir**|Nesne her zaman bir işlem akışını kök bileşeni özniteliği makrosu custom(TLBATTR_TRANS_REQNEW,0) .h dosyası (öznitelikli projeler) veya (nonattributed projeler) .idl dosyasına ekleyerek olduğunu belirtir.|

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM+ 1.0 Bileşeni Sihirbazı](../../atl/reference/atl-com-plus-1-0-component-wizard.md)<br/>
[ATL COM + 1.0 bileşeni](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)
