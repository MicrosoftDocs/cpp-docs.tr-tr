---
title: 'MFC ActiveX denetimleri: Seri hale getirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- _wVerMinor
- DoPropExchange
- _wVerMajor
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], version support
- wVerMinor global constant [MFC]
- GetVersion method [MFC]
- ExchangeVersion method [MFC]
- MFC ActiveX controls [MFC], serializing
- DoPropExchange method [MFC]
- versioning ActiveX controls
- wVerMajor global constant
ms.assetid: 9d57c290-dd8c-4853-b552-6f17f15ebedd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9db6ff6c0cdda01875e4968e4d92ca087ad2b57
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930067"
---
# <a name="mfc-activex-controls-serializing"></a>MFC ActiveX Denetimleri: Seri Hale Getirme
Bu makalede bir ActiveX denetimini serileştirmek nasıl anlatılmaktadır. Seri hale getirme okuma veya bir disk dosyası gibi bir kalıcı depolama ortamına yazma işlemidir. Microsoft Foundation Class (MFC) kitaplığı, sınıfında serileştirilmesi için yerleşik destek sağlar. `CObject`. `COleControl` Bu destek ActiveX denetimlerine özelliği değişimi mekanizması kullanımı ile uzatır.  
  
 Seri hale getirme ActiveX denetimleri için geçersiz kılarak uygulanır [COleControl::DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange). Bu işlev yüklemesi sırasında çağrılır ve Denetim nesnesinin kaydetme üye değişkeni veya bir üye değişkenine değişiklik bildirimi ile uygulanan tüm özellikler depolar.  
  
 Aşağıdaki konular bir ActiveX denetimini serileştirmek için ilgili ana sorunlarını ele alır:  
  
-   Uygulama `DoPropExchange` denetim nesneyi serileştirmek için işlevi  
  
-   [Seri hale getirme işlemi özelleştirme](#_core_customizing_the_default_behavior_of_dopropexchange)  
  
-   [Sürüm desteği sağlama](#_core_implementing_version_support)  
  
##  <a name="_core_implementing_the_dopropexchange_function"></a> DoPropExchange işlevini uygulama  
 Denetim projesi oluşturmak için ActiveX Denetim Sihirbazı'nı kullandığınızda, birkaç varsayılan işleyici işlevleri otomatik olarak varsayılan uygulaması da dahil olmak üzere denetim sınıfına eklenir [COleControl::DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange). Aşağıdaki örnek ActiveX Denetim Sihirbazı ile oluşturulan sınıflar için eklenen kod gösterir:  
  
 [!code-cpp[NVC_MFC_AxUI#43](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_1.cpp)]  
  
 Bir özellik kalıcı yapmak istiyorsanız, değişiklik `DoPropExchange` özelliği exchange işlevi çağrısı ekleyerek düzenleyin. Aşağıdaki örnek, CircleShape özelliğinin varsayılan değeri olduğu özel bir Boolean CircleShape özellik serileştirmek gösterir **TRUE**:  
  
 [!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]  
[!code-cpp[NVC_MFC_AxSer#2](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_3.cpp)]  
  
 Aşağıdaki tabloda, denetimin özelliklerini seri hale getirmek için kullanabileceğiniz olası özellik exchange işlevleri listelenmektedir:  
  
|Özellik değişimi işlevleri|Amaç|  
|---------------------------------|-------------|  
|**PX_Blob)**|İkili büyük nesne (BLOB) veri özelliği türü serileştirir.|  
|**PX_Bool)**|Türü Boolean özelliği serileştirir.|  
|**PX_Color)**|Tür renk özelliği serileştirir.|  
|**PX_Currency)**|Bir tür serileştiren **CY** (para birimi) özelliği.|  
|**PX_Double)**|Bir tür serileştiren **çift** özelliği.|  
|**PX_Font)**|Yazı tipi type özelliği serileştirir.|  
|**PX_Float)**|Bir tür serileştiren **float** özelliği.|  
|**Px_ıunknown)**|Türünde bir özellik serileştiren `LPUNKNOWN`.|  
|**PX_Long)**|Bir tür serileştiren **uzun** özelliği.|  
|**PX_Picture)**|Türü resim özelliği serileştirir.|  
|**PX_Short)**|Bir tür serileştiren **kısa** özelliği.|  
|**PXstring)**|Bir tür serileştiren `CString` özelliği.|  
|**PX_ULong)**|Bir tür serileştiren **ULONG** özelliği.|  
|**PX_UShort)**|Bir tür serileştiren **USHORT** özelliği.|  
  
 Bu özellik exchange işlevler hakkında daha fazla bilgi için bkz: [Kalıcılık, OLE denetimleri](../mfc/reference/persistence-of-ole-controls.md) içinde *MFC başvurusu*.  
  
##  <a name="_core_customizing_the_default_behavior_of_dopropexchange"></a> DoPropExchange varsayılan davranışını özelleştirme  
 Varsayılan uygulaması `DoPropertyExchange` (gösterildiği gibi önceki konu) temel sınıfı için bir çağrı yapar `COleControl`. Bu otomatik olarak tarafından desteklenen özellikler kümesini serileştiren `COleControl`, yalnızca özel denetimi özellikleri, seri hale getirme'den daha fazla depolama alanı kullanır. Bu çağrı kaldırma yalnızca önemli olduğunu düşündüğünüz özellikleri serileştirmek üzere nesnenizin sağlar. Denetime uygulanan tüm stok özellik durumları açıkça eklemedikçe denetim nesnesi yüklenirken veya kaydederken serileştirilecek değil **PX_** kendileri için çağırır.  
  
##  <a name="_core_implementing_version_support"></a> Sürüm desteği sağlama  
 Sürüm desteği yeni kalıcı özellikleri ekleyin ve hala algılamak ve denetim önceki bir sürümü tarafından oluşturulmuş kalıcı durumunu yükleyemediğini yeniden düzenlenen bir ActiveX denetimi sağlar. Bir denetimin sürüm kullanılabilir hale getirmek kalıcı verilerini bir parçası olarak, arama [COleControl::ExchangeVersion](../mfc/reference/colecontrol-class.md#exchangeversion) denetimin içinde `DoPropExchange` işlevi. ActiveX denetimini ActiveX Denetim Sihirbazı'nı kullanarak oluşturduysanız bu çağrı otomatik olarak eklenir. Sürüm desteği gerekmiyorsa kaldırılabilir. Ancak, Denetim boyutu çok maliyetidir küçük (4 bayt) sürüm desteği sağlayan esneklik eklenmiştir.  
  
 Denetim ActiveX Denetim Sihirbazı'nı kullanarak oluşturulmamışsa bir çağrı ekleyin `COleControl::ExchangeVersion` başında aşağıdaki satırı ekleyerek, `DoPropExchange` işlevi (çağırmadan önce `COleControl::DoPropExchange`):  
  
 [!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]  
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]  
  
 Kullanabilirsiniz **DWORD** sürüm numarası olarak. ActiveX Denetim Sihirbazı tarafından oluşturulan projeleri kullanmak `_wVerMinor` ve `_wVerMajor` varsayılan olarak. Bu projenin ActiveX denetimi sınıfı uygulama dosyasında tanımlanan genel sabittir. Geri kalan içinde `DoPropExchange` işlevi, çağırabilir [CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion) kaydetmeden veya alma sürümünü almak için herhangi bir zamanda.  
  
 Aşağıdaki örnekte, bu örnek denetiminin 1 sürümü yalnızca bir "ReleaseDate" özelliğe sahiptir. Sürüm 2 "OriginalDate" özelliği ekler. Eski sürümden kalıcı durumunu yüklemek için Denetim istenirse, varsayılan bir değer için yeni bir özellik için üye değişkeni başlatır.  
  
 [!code-cpp[NVC_MFC_AxSer#4](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_5.cpp)]  
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]  
  
 Varsayılan olarak, bir denetim "eski verileri en son biçime dönüştürür". Sürüm 2 denetimi sürüm 1'tarafından kaydedilmiş olan veri yüklerse, yeniden kaydedildiğinde, örneğin, bu sürüm 2 biçimi yazacaksınız. Veri biçimi son okuma kaydetmek için denetim isterseniz, geçirmek **FALSE** çağrılırken üçüncü parametre olarak `ExchangeVersion`. Bu üçüncü parametre isteğe bağlıdır ve **TRUE** varsayılan olarak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

