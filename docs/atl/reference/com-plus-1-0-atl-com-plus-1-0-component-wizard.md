---
title: "COM + 1.0, ATL COM + 1.0 Bileşen Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.codewiz.class.atl.mts.options
dev_langs: C++
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 102e6a0a9b7055000d051f5fb729dd45863a16cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="com-10-atl-com-10-component-wizard"></a>COM + 1.0, ATL COM + 1.0 Bileşen Sihirbazı
Sihirbazın bu sayfası ATL COM + 1.0 bileşen arabirim türü ve ek arabirimler desteklenecek belirtmek için kullanın.  
  
 ATL projeleri ve ATL COM sınıfları hakkında daha fazla bilgi için bkz: [ATL COM Masaüstü bileşenleri](../../atl/atl-com-desktop-components.md).  
  
 **Arabirimi**  
 Nesne destekleyen arabirimi türünü belirtir. Varsayılan olarak, bir çift arabirim nesnesi destekler.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Çift**|Nesne çift arabirim desteği belirtir (kendi vtable özel arabirimi işlevleri ve geç bağlama sahip `IDispatch` yöntemleri). COM istemcilerinde ve Otomasyon denetleyicileri nesneye erişim sağlar.|  
|**Özel**|Nesne (kendi vtable özel arabirimi işlevleri vardır) özel bir arabirim desteklediğini belirtir. Özel bir arabirim özellikle işlem sınırları boyunca bir çift arabirim hızlı olabilir.<br /><br /> -   **Otomasyon uyumlu** özel arabirim Otomasyon desteği ekler. Öznitelikli projeleri için ayarlar **oleautomation** coclass özniteliği.|  
  
 **Kuyruğa atılabilir**  
 İstemcilerin zaman uyumsuz ileti sıraları kullanarak bu bileşeni çağırabilirsiniz gösterir. Öznitelikli bileşen makrosu özel (TLBATTR_QUEUEABLE, 0) .h dosyası (öznitelikli projeleri) veya (nonattributed projeleri) .idl dosyasına ekler.  
  
 **Destek**  
 Hata işleme ve nesne denetimi için ek destek gösterir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**ISupportErrorInfo**|Desteği oluşturur [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) nesne istemciye hata bilgilerini dönebilmeniz arabirim.|  
|**IObjectControl**|Üç nesne erişiminizi sağlayan [IObjectControl](http://msdn.microsoft.com/library/windows/desktop/ms686474) yöntemleri: [etkinleştirme](http://msdn.microsoft.com/library/windows/desktop/ms681303), [CanBePooled](http://msdn.microsoft.com/library/windows/desktop/ms684322), ve [etkinliğini](http://msdn.microsoft.com/library/windows/desktop/ms687094).|  
|**IObjectConstruct'ı**|Desteği oluşturur [IObjectConstruct'ı](http://msdn.microsoft.com/library/windows/desktop/ms680583) geçirme parametreleri diğer yöntemleri veya nesneleri yönetmek için arabirim.|  
  
 **İşlem**  
 Nesne işlemleri desteklediğini belirtir. Dosya mtxattr.h .idl dosyasında (nonattributed projeleri) içerir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Desteklenen**|Nesne hiçbir zaman bir işlem akışı kökündeki .h dosyası (öznitelikli projeleri) veya .idl dosyasına (nonattributed projeleri) bileşeni özniteliği makrosu custom(TLBATTR_TRANS_SUPPORTED,0) ekleyerek olduğunu belirtir.|  
|**Gerekli**|Nesne olabilir veya bir işlem akışı kökündeki .h dosyası (öznitelikli projeleri) veya .idl dosyasına (nonattributed projeleri) bileşeni özniteliği makrosu custom(TLBATTR_TRANS_REQUIRED,0) ekleyerek olmayabilir belirtir.|  
|**Desteklenmiyor**|Nesne işlemleri dışlar belirtir. Bileşen özniteliği makrosu custom(TLBATTR_TRANS_NOTSUPP,0) .h dosyası (öznitelikli projeleri) veya (nonattributed projeleri) .idl dosyasına ekler.|  
|**Yeni gerektirir**|Nesne her zaman bir işlem akışı kökündeki .h dosyası (öznitelikli projeleri) veya .idl dosyasına (nonattributed projeleri) bileşeni özniteliği makrosu custom(TLBATTR_TRANS_REQNEW,0) ekleyerek olduğunu belirtir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL COM + 1.0 Bileşen Sihirbazı](../../atl/reference/atl-com-plus-1-0-component-wizard.md)   
 [ATL COM + 1.0 bileşeni](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)

