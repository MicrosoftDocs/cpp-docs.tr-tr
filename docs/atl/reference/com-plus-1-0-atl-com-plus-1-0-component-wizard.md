---
title: COM + 1.0, ATL COM + 1.0 bileşeni Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.mts.options
dev_langs:
- C++
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b70589829ec75712eedde86b71d90f0eec46fba
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43754675"
---
# <a name="com-10-atl-com-10-component-wizard"></a>COM + 1.0, ATL COM + 1.0 bileşeni Sihirbazı

ATL COM + 1.0 bileşeni Sihirbazı bu sayfanın bir arabirim türüne ve ek arabirimleri desteklenecek belirtmek için kullanın.

ATL projeleri ve ATL COM sınıfları hakkında daha fazla bilgi için bkz. [ATL COM Masaüstü bileşenleri](../../atl/atl-com-desktop-components.md).

**Arabirimi**  
Nesne destekleyen arabirim türünü belirtir. Varsayılan olarak, nesne çift arabirim destekler.

|Seçenek|Açıklama|
|------------|-----------------|
|**Çift**|Nesne çift arabirim desteklediğini belirtir (özel arabirim işlevi ve geç bağlama, vtable olan `IDispatch` yöntemleri). COM istemcilerinde ve Otomasyon denetleyicileri nesneye erişim sağlar.|
|**Özel**|Nesne (özel arabirim işlevleri kendi vtable sahiptir) özel bir arabirim desteklediğini belirtir. Özel arabirim özellikle işlem sınırları arasında çift arabirim, daha hızlı olabilir.<br /><br /> -   **Otomasyon uyumlu** özel Otomasyon desteği ekler. Öznitelikli projeler için ayarlar **oleautomation** coclass özniteliği.|

**Kuyruğa atılabilir**  
İstemcilerin zaman uyumsuz ileti kuyrukları kullanarak bu bileşeni çağırabilirsiniz gösterir. Öznitelikli bileşen makrosu özel (TLBATTR_QUEUEABLE, 0) .h dosyası (öznitelikli projeler) veya .idl dosyasına (nonattributed projeler) ekler.

**Destek**  
Hata işleme ve nesne denetimi için ek destek gösterir.

|Seçenek|Açıklama|
|------------|-----------------|
|**ISupportErrorInfo**|Desteği oluşturur [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) istemciye hata bilgilerini nesnenin dönebilmeniz arabirim.|
|**IObjectControl**|Üç nesne erişiminizi sağlayan [IObjectControl](/windows/desktop/api/comsvcs/nn-comsvcs-iobjectcontrol) yöntemleri: [etkinleştirme](/windows/desktop/api/comsvcs/nf-comsvcs-iobjectcontrol-activate), [CanBePooled](/windows/desktop/api/comsvcs/nf-comsvcs-iobjectcontrol-canbepooled), ve [devre dışı bırak](/windows/desktop/api/comsvcs/nf-comsvcs-iobjectcontrol-deactivate).|
|**IObjectConstruct'ı**|Desteği oluşturur [IObjectConstruct'ı](/windows/desktop/api/comsvcs/nn-comsvcs-iobjectconstruct) geçirme parametrelerinde diğer yöntemleri veya nesneleri yönetmek için arabirim.|

**İşlem**  
Nesne işlemleri desteklediğini belirtir. Dosya mtxattr.h .idl dosyasında (nonattributed projeler) içerir.

|Seçenek|Açıklama|
|------------|-----------------|
|**Desteklenen**|Nesne hiçbir zaman bir işlem akışını kök bileşeni özniteliği makrosu custom(TLBATTR_TRANS_SUPPORTED,0) .h dosyası (öznitelikli projeler) veya (nonattributed projeler) .idl dosyasına ekleyerek olduğunu belirtir.|
|**Gerekli**|Nesne olabilir veya bir işlem akışını kök bileşeni özniteliği makrosu custom(TLBATTR_TRANS_REQUIRED,0) .h dosyası (öznitelikli projeler) veya (nonattributed projeler) .idl dosyasına ekleyerek olmayabilir belirtir.|
|**Desteklenmiyor**|Nesne işlemleri hariç belirtir. Bileşen özniteliği makrosu custom(TLBATTR_TRANS_NOTSUPP,0) .h dosyası (öznitelikli projeler) veya .idl dosyasına (nonattributed projeler) ekler.|
|**Yeni gerektirir**|Nesne her zaman bir işlem akışını kök bileşeni özniteliği makrosu custom(TLBATTR_TRANS_REQNEW,0) .h dosyası (öznitelikli projeler) veya (nonattributed projeler) .idl dosyasına ekleyerek olduğunu belirtir.|

## <a name="see-also"></a>Ayrıca Bkz.

[ATL COM + 1.0 bileşeni Sihirbazı](../../atl/reference/atl-com-plus-1-0-component-wizard.md)   
[ATL COM + 1.0 bileşeni](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)

