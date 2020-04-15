---
title: 'MFC ActiveX Denetimleri: Seri Hale Getirme'
ms.date: 09/12/2018
f1_keywords:
- _wVerMinor
- DoPropExchange
- _wVerMajor
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
ms.openlocfilehash: d804486b612906f537b6ed1665dfc0cec5149826
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364543"
---
# <a name="mfc-activex-controls-serializing"></a>MFC ActiveX Denetimleri: Seri Hale Getirme

Bu makalede, ActiveX denetiminin nasıl serileştirilen anlatılmaktadır. Serileştirme, disk dosyası gibi kalıcı bir depolama ortamına okuma veya yazma işlemidir. Microsoft Hazırlık Sınıfı (MFC) Kitaplığı, sınıfta `CObject`serileştirme için yerleşik destek sağlar. `COleControl`bu desteği bir özellik değiştirme mekanizması kullanarak ActiveX denetimlerine genişletir.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. ActiveX'in yerini alabilecek modern teknolojiler hakkında daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

ActiveX denetimleri için serileştirme [COleControl::DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange)geçersiz kılınarak uygulanır. Denetim nesnesinin yüklenmesi ve kaydedilmesi sırasında çağrılan bu işlev, uygulanan tüm özellikleri bir üye değişken veya değişiklik bildirimi ile bir üye değişkenle depolar.

Aşağıdaki konular ActiveX denetiminin serileştirilmesiyle ilgili temel konuları kapsamaktadır:

- Denetim `DoPropExchange` nesnenizi seri hale getirmek için işlev uygulama

- [Serileştirme İşlemini Özelleştirme](#_core_customizing_the_default_behavior_of_dopropexchange)

- [Sürüm Desteği Uygulama](#_core_implementing_version_support)

## <a name="implementing-the-dopropexchange-function"></a><a name="_core_implementing_the_dopropexchange_function"></a>DoPropExchange Fonksiyonunun Uygulanması

Denetim projesini oluşturmak için ActiveX Denetim Sihirbazı'nı kullandığınızda, [COleControl::DoPropExchange'in](../mfc/reference/colecontrol-class.md#dopropexchange)varsayılan uygulaması da dahil olmak üzere denetim sınıfına otomatik olarak birkaç varsayılan işleyici işlevi eklenir. Aşağıdaki örnekte ActiveX Denetim Sihirbazı ile oluşturulan sınıflara eklenen kod gösterilmektedir:

[!code-cpp[NVC_MFC_AxUI#43](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_1.cpp)]

Bir özelliği kalıcı hale getirmek `DoPropExchange` istiyorsanız, özellik değişimi işlevine bir çağrı ekleyerek değiştirin. Aşağıdaki örnek, CircleShape özelliğinin **VARSAYıLAN TRUE**değerine sahip olduğu özel bir Boolean CircleShape özelliğinin serileştirilmesini gösterir:

[!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#2](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_3.cpp)]

Aşağıdaki tablo, denetimin özelliklerini seri hale getirmek için kullanabileceğiniz olası özellik değişimi işlevlerini listeler:

|Özellik değiştirme işlevleri|Amaç|
|---------------------------------|-------------|
|**PX_Blob ( )**|Bir tür İkili Büyük Nesne (BLOB) veri özelliğini serileştirir.|
|**PX_Bool ( )**|Boolean türüne serileştirir.|
|**PX_Color( )**|Bir tür renk özelliğini seri hale leştirir.|
|**PX_Currency ( )**|**Cy** (para birimi) özelliğini seri hale leştirir.|
|**PX_Double ( )**|Seri bir tür **çift** özelliği.|
|**PX_Font ( )**|Yazı Tipi türü özelliğini seri hale leştirir.|
|**PX_Float ( )**|Bir tür **float** özelliğini seri hale leştirir.|
|**PX_IUnknown ( )**|Türünde `LPUNKNOWN`bir özelliği serileştirir.|
|**PX_Long ( )**|Bir tür **uzun** özelliği serializes.|
|**PX_Picture ( )**|Bir tür Resim özelliğini seri hale leştirir.|
|**PX_Short ( )**|Bir tür **kısa** özelliğiserializes.|
|**PXstring( )**|Bir tür `CString` özelliğini seri hale leştirir.|
|**PX_ULong ( )**|Bir Tür **ULONG** özelliğini seri hale leştirir.|
|**PX_UShort ( )**|Bir Tür **USHORT** özelliğini seri hale leştirir.|

Bu özellik değiştirme işlevleri hakkında daha fazla bilgi için, *MFC Başvurusu'nda* [OLE Denetimlerinin Kalıcılığı'na](../mfc/reference/persistence-of-ole-controls.md) bakın.

## <a name="customizing-the-default-behavior-of-dopropexchange"></a><a name="_core_customizing_the_default_behavior_of_dopropexchange"></a>DoPropExchange'in Varsayılan Davranışını Özelleştirme

Varsayılan uygulama `DoPropertyExchange` (önceki konuda gösterildiği gibi) taban sınıfa `COleControl`bir çağrı yapar. `COleControl`Bu, yalnızca denetimin özel özelliklerini serihale etmekten daha fazla depolama alanı kullanan, otomatik olarak desteklenen özellikler kümesini seri hale leştirir. Bu çağrıyı kaldırmak, nesnenizin yalnızca önemli olduğunu düşündüğünüz özellikleri seri hale leştirmesine olanak tanır. Denetimin uyguladığı herhangi bir stok özelliği, denetim nesnesini kaydederken veya yüklerken, onlar için **açıkça PX_** çağrıları eklemediğiniz sürece serileştirilmez.

## <a name="implementing-version-support"></a><a name="_core_implementing_version_support"></a>Sürüm Desteği Uygulama

Sürüm desteği, yeni kalıcı özellikler eklemek için gözden geçirilmiş bir ActiveX denetimi sağlar ve denetimin önceki bir sürümü tarafından oluşturulan kalıcı durumu algılamak ve yüklemek için de kullanılabilir. Bir denetimsürümünü kalıcı verilerinin bir parçası olarak kullanılabilir hale getirmek için, denetimin `DoPropExchange` işlevinde [COleControl::ExchangeVersion'u](../mfc/reference/colecontrol-class.md#exchangeversion) arayın. ActiveX Denetim Sihirbazı kullanılarak ActiveX denetimi oluşturulduysa, bu çağrı otomatik olarak eklenir. Sürüm desteği gerekmese kaldırılabilir. Ancak, sürüm desteğinin sağladığı ek esneklik için denetim boyutundaki maliyet çok küçüktür (4 bayt).

Denetim ActiveX Denetim Sihirbazı ile oluşturulmamadıysa, `COleControl::ExchangeVersion` işlevinizin `DoPropExchange` başına aşağıdaki satırı ekleyerek (aramadan `COleControl::DoPropExchange`önce):

[!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

Herhangi bir **DWORD'u** sürüm numarası olarak kullanabilirsiniz. ActiveX Denetim Sihirbazı tarafından `_wVerMinor` `_wVerMajor` oluşturulan projeler varsayılan olarak. Bunlar, projenin ActiveX denetim sınıfının uygulama dosyasında tanımlanan genel sabitlerdir. İşlevinizin `DoPropExchange` geri kalanında, kaydettiğiniz veya aldığınız sürümü almak için istediğiniz zaman [CPropExchange::GetVersion'u](../mfc/reference/cpropexchange-class.md#getversion) arayabilirsiniz.

Aşağıdaki örnekte, bu örnek denetiminin sürüm 1 yalnızca bir "ReleaseDate" özelliği vardır. Sürüm 2 bir "OriginalDate" özelliği ekler. Denetim, kalıcı durumu eski sürümden yüklemesi için talimat vereliyse, yeni özellik için üye değişkeni varsayılan bir değere başolarak alır.

[!code-cpp[NVC_MFC_AxSer#4](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_5.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

Varsayılan olarak, bir denetim eski verileri en son biçime "dönüştürür". Örneğin, bir denetimin sürüm 2 sürümü, sürüm 1 tarafından kaydedilen verileri yüklerse, yeniden kaydedildiğinde sürüm 2 biçimini yazar. Denetimin son okuma biçiminde veri kaydetmesini istiyorsanız, ararken `ExchangeVersion` **FALSE'u** üçüncü bir parametre olarak geçirin. Bu üçüncü parametre isteğe bağlıdır ve varsayılan olarak **TRUE'dur.**

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)
