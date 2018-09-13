---
title: 'MFC ActiveX denetimleri: Seri hale getirme | Microsoft Docs'
ms.custom: ''
ms.date: 09/12/2018
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
ms.openlocfilehash: 6fb70b11fc1a926914fe661607f18259a0608c85
ms.sourcegitcommit: b4432d30f255f0cb58dce69cbc8cbcb9d44bc68b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45535073"
---
# <a name="mfc-activex-controls-serializing"></a>MFC ActiveX Denetimleri: Seri Hale Getirme
Bu makalede, bir ActiveX denetimini serileştirmek anlatılmaktadır. Seri hale getirme okuma veya bir disk dosyası gibi bir kalıcı depolama ortamı için yazma işlemidir. Microsoft Foundation Class (MFC) kitaplığı, sınıf serileştirme için yerleşik destek sağlar. `CObject`. `COleControl` Bu destek özelliği değişimi mekanizması kullanılarak ActiveX denetimlerine genişletir.

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerini modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).  
  
 ActiveX denetimleri için serileştirme geçersiz kılarak gerçekleştirilir [COleControl::DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange). Bu işlev, yükleme sırasında çağrılır ve bir üye değişkeni veya bir üye değişkeni değişiklik bildirimi ile uygulanan tüm özellikler denetimi nesnesinin kaydetme depolar.  
  
 Aşağıdaki konular bir ActiveX denetimini serileştirmek için ilgili ana sorunlarını ele alır:  
  
-   Uygulama `DoPropExchange` denetim nesneyi serileştirmek için işlevi  
  
-   [Seri hale getirme işlemini özelleştirme](#_core_customizing_the_default_behavior_of_dopropexchange)  
  
-   [Uygulama sürüm desteği](#_core_implementing_version_support)  
  
##  <a name="_core_implementing_the_dopropexchange_function"></a> DoPropExchange işlevini uygulama  
 Denetimi projesi oluşturmak için ActiveX Denetim Sihirbazı'nı kullandığınızda, birkaç varsayılan işleyici işlevleri otomatik olarak varsayılan uygulaması da dahil olmak üzere denetim sınıfına eklenen [COleControl::DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange). Aşağıdaki örnek ActiveX Denetim Sihirbazı ile oluşturulan sınıflar için eklenen kodu gösterir:  
  
 [!code-cpp[NVC_MFC_AxUI#43](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_1.cpp)]  
  
 Bir özellik kalıcı hale getirmek isterseniz değiştirme `DoPropExchange` ekleyerek özelliği exchange işlevi çağrısı. Aşağıdaki örnek, CircleShape özelliği varsayılan değerine sahip olduğu bir özel Boole CircleShape özellik serileştirmek gösterir **TRUE**:  
  
 [!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]  
[!code-cpp[NVC_MFC_AxSer#2](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_3.cpp)]  
  
 Aşağıdaki tabloda, denetimin özelliklerini seri hale getirmek için kullanabileceğiniz olası özelliği değişimi işlevleri listelenmektedir:  
  
|Özelliği değişimi işlevleri|Amaç|  
|---------------------------------|-------------|  
|**PX_Blob)**|İkili büyük nesne (BLOB) veri özelliği türü serileştirir.|  
|**PX_Bool)**|Bir Boolean özelliği türü serileştirir.|  
|**PX_Color)**|Türü color özelliğine serileştirir.|  
|**PX_Currency)**|Bir tür serileştiren **CY** (para birimi) özelliği.|  
|**PX_Double)**|Bir tür serileştiren **çift** özelliği.|  
|**PX_Font)**|Bir yazı tipi tür özelliği serileştirir.|  
|**PX_Float)**|Bir tür serileştiren **float** özelliği.|  
|**Px_ıunknown)**|Vlastnost typu serileştiren `LPUNKNOWN`.|  
|**PX_Long)**|Bir tür serileştiren **uzun** özelliği.|  
|**PX_Picture)**|Bir tür resim özelliği serileştirir.|  
|**PX_Short)**|Bir tür serileştiren **kısa** özelliği.|  
|**PXstring)**|Bir tür serileştiren `CString` özelliği.|  
|**PX_ULong)**|Bir tür serileştiren **ULONG** özelliği.|  
|**PX_UShort)**|Bir tür serileştiren **USHORT** özelliği.|  
  
 Bu özellik değişim işlevleri hakkında daha fazla bilgi için bkz. [Kalıcılık, OLE denetimleri](../mfc/reference/persistence-of-ole-controls.md) içinde *MFC başvurusu*.  
  
##  <a name="_core_customizing_the_default_behavior_of_dopropexchange"></a> DoPropExchange varsayılan davranışını özelleştirme  
 Varsayılan uygulaması `DoPropertyExchange` (bir önceki konu gösterildiği gibi) temel sınıf için bir çağrı yapar `COleControl`. Bu otomatik olarak tarafından desteklenen özellikler kümesini serileştiren `COleControl`, denetimin için özel özellikleri serileştirmek daha fazla depolama alanı kullanır. Bu çağrı kaldırma önemli olduğunu düşündüğünüz özellikleri serileştirmek üzere nesnenizin sağlar. Denetimi uygulanan bir stok özellik durum kaydetme ya da açıkça eklemediğiniz sürece denetim nesnesi yükleniyor serileştirilecek değil **PX_** kendileri için çağırır.  
  
##  <a name="_core_implementing_version_support"></a> Uygulama sürüm desteği  
 Sürekli yeni özellikler ekleyebilir ve hala algılamak ve denetim önceki bir sürümü tarafından oluşturulmuş kalıcı durum yük düzeltilmiş bir ActiveX denetimi sürüm desteği sağlar. Denetim sürümü kullanılabilir hale getirmek için kalıcı verilerini bir parçası olarak, çağrı [COleControl::ExchangeVersion](../mfc/reference/colecontrol-class.md#exchangeversion) denetimin içindeki `DoPropExchange` işlevi. ActiveX denetimini ActiveX Denetim Sihirbazı'nı kullanarak oluşturduysanız bu çağrı otomatik olarak eklenir. Sürüm desteği gerekmiyorsa kaldırılabilir. Bununla birlikte, Denetim boyutu maliyeti çok mu (4 bayt) küçük sürüm desteği sağlayan eklenen esnekliği sağlar.  
  
 Bir çağrı ekleyin, denetimi ile ActiveX Denetim Sihirbazı'nı oluşturulmamışsa `COleControl::ExchangeVersion` başında aşağıdaki satırı ekleyerek, `DoPropExchange` işlevi (çağırmadan önce `COleControl::DoPropExchange`):  
  
 [!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]  
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]  
  
 Kullanabilirsiniz **DWORD** sürüm numarası olarak. ActiveX Denetim Sihirbazı tarafından oluşturulan projeleri kullanmak `_wVerMinor` ve `_wVerMajor` varsayılan olarak. Bu projenin ActiveX denetimi sınıf uygulama dosyasında tanımlanan genel sabittir. İçinde geri kalanında, `DoPropExchange` işlevi çağırabilir [CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion) kaydetme veya alma sürümü almak için herhangi bir zamanda.  
  
 Aşağıdaki örnekte, bu örnek denetimin sürüm 1 yalnızca "ReleaseDate" özelliğine sahiptir. Sürüm 2 "OriginalDate" özelliği ekler. Kalıcı durum eski sürümü yüklemek için Denetim belirtilmedikçe varsayılan bir değerle yeni bir özellik için üye değişkeni başlatır.  
  
 [!code-cpp[NVC_MFC_AxSer#4](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_5.cpp)]  
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]  
  
 Varsayılan olarak, bir denetim "eski verileri en son biçime dönüştürür". Sürüm 2 denetimi sürüm 1'tarafından kaydedilmiş olan veri yüklerse, tekrar kaydedildiğinde, bu sürüm 2 biçimi yazılacaktır. Veri biçimi son okuma kaydetmek için denetleme isterseniz, geçmesi **FALSE** çağırırken üçüncü parametre olarak `ExchangeVersion`. Bu üçüncü parametresi isteğe bağlıdır ve **TRUE** varsayılan olarak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

