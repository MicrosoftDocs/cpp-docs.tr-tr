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
ms.openlocfilehash: f5e3b4bdf203f90b3550a2521ba51ba451cf3a46
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225026"
---
# <a name="mfc-activex-controls-serializing"></a>MFC ActiveX Denetimleri: Seri Hale Getirme

Bu makalede bir ActiveX denetiminin serileştirilme yöntemi anlatılmaktadır. Serileştirme, disk dosyası gibi kalıcı bir depolama ortamını okuma veya yazma işlemidir. Microsoft Foundation Class (MFC) kitaplığı, sınıfında serileştirme için yerleşik destek sağlar `CObject` . `COleControl`Özellik değişim mekanizması kullanılarak bu desteği ActiveX denetimlerine genişletir.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

ActiveX denetimleri için serileştirme, [Coelcontrol::D oPropExchange](reference/colecontrol-class.md#dopropexchange)tarafından geçersiz kılınarak uygulanır. Denetim nesnesinin yüklenmesi ve kaydedilmesi sırasında çağrılan bu işlev, bir üye değişkeni veya değişiklik bildirimi olan bir üye değişkeni ile uygulanan tüm özellikleri depolar.

Aşağıdaki konularda bir ActiveX denetiminin serileştirilmesi ile ilgili başlıca sorunlar ele alınmaktadır:

- `DoPropExchange`Denetim nesneniz seri hale getirmek için işlev uygulama

- [Serileştirme Işlemini özelleştirme](#_core_customizing_the_default_behavior_of_dopropexchange)

- [Sürüm desteğini uygulama](#_core_implementing_version_support)

## <a name="implementing-the-dopropexchange-function"></a><a name="_core_implementing_the_dopropexchange_function"></a>DoPropExchange Işlevini uygulama

Denetim projesini oluşturmak için ActiveX Denetim Sihirbazı 'Nı kullandığınızda, [COleControl::D oPropExchange](reference/colecontrol-class.md#dopropexchange)'in varsayılan uygulanması dahil olmak üzere, çeşitli varsayılan işleyici işlevleri denetim sınıfına otomatik olarak eklenir. Aşağıdaki örnek, ActiveX Denetim Sihirbazı ile oluşturulan sınıflara eklenen kodu gösterir:

[!code-cpp[NVC_MFC_AxUI#43](codesnippet/cpp/mfc-activex-controls-serializing_1.cpp)]

Bir özelliği kalıcı hale getirmek istiyorsanız, `DoPropExchange` Özellik değişim işlevine bir çağrı ekleyerek değiştirin. Aşağıdaki örnek, bir özel Boolean CircleShape özelliğinin serileştirmesini gösterir; burada, CircleShape özelliğinin varsayılan değeri **true 'dur**:

[!code-cpp[NVC_MFC_AxSer#1](codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#2](codesnippet/cpp/mfc-activex-controls-serializing_3.cpp)]

Aşağıdaki tabloda, denetimin özelliklerini seri hale getirmek için kullanabileceğiniz olası Özellik değişim işlevleri listelenmektedir:

|Özellik değişim işlevleri|Amaç|
|---------------------------------|-------------|
|**PX_Blob ()**|Tür Ikili büyük nesne (BLOB) veri özelliğini seri hale getirir.|
|**PX_Bool ()**|Bir tür Boolean özelliğini seri hale getirir.|
|**PX_Color ()**|Bir tür rengi özelliğini seri hale getirir.|
|**PX_Currency ()**|Bir tür **Cy** (para birimi) özelliğini seri hale getirir.|
|**PX_Double ()**|Bir tür özelliğini seri hale getirir **`double`** .|
|**PX_Font ()**|Yazı tipi türü özelliğini seri hale getirir.|
|**PX_Float ()**|Bir tür özelliğini seri hale getirir **`float`** .|
|**PX_IUnknown ()**|Türünde bir özelliği seri hale getirir `LPUNKNOWN` .|
|**PX_Long ()**|Bir tür özelliğini seri hale getirir **`long`** .|
|**PX_Picture ()**|Bir tür resim özelliğini seri hale getirir.|
|**PX_Short ()**|Bir tür özelliğini seri hale getirir **`short`** .|
|**PXstring ()**|Bir tür özelliğini seri hale getirir `CString` .|
|**PX_ULong ()**|Bir tür **ulong** özelliği seri hale getirir.|
|**PX_UShort ()**|Bir tür **ushort** özelliğini seri hale getirir.|

Bu özellik değişim işlevleri hakkında daha fazla bilgi için bkz. *MFC başvurusunda* [OLE denetimlerinin kalıcılığı](reference/persistence-of-ole-controls.md) .

## <a name="customizing-the-default-behavior-of-dopropexchange"></a><a name="_core_customizing_the_default_behavior_of_dopropexchange"></a>DoPropExchange 'in varsayılan davranışını özelleştirme

Varsayılan uygulamasının `DoPropertyExchange` (önceki konu başlığında gösterildiği gibi) temel sınıfa bir çağrı yapar `COleControl` . Bu, tarafından otomatik olarak desteklenen özellikler kümesini serileştirerek `COleControl` , yalnızca denetimin özel özelliklerini serileştirilenden daha fazla depolama alanı kullanır. Bu çağrıyı kaldırmak, nesnenizin yalnızca önemli olduğunu düşündüğünüz özellikleri serileştirmek için izin verir. Tüm hisse senedi özellik durumları, bu denetim nesnesi için açıkça **px_** çağrılar eklemediğiniz takdirde denetim nesnesi kaydedilirken veya yüklenirken serileştirilmez.

## <a name="implementing-version-support"></a><a name="_core_implementing_version_support"></a>Sürüm desteğini uygulama

Sürüm desteği, düzeltilmiş bir ActiveX denetiminin yeni kalıcı özellikler eklemesine olanak sağlar ve denetimin önceki bir sürümü tarafından oluşturulan kalıcı durumu tespit edebilir ve yükleyebilir. Bir denetimin sürümünü kalıcı verilerin bir parçası olarak kullanılabilir hale getirmek için, denetimin işlevinde [Cotacontrol:: ExchangeVersion](reference/colecontrol-class.md#exchangeversion) öğesini çağırın `DoPropExchange` . ActiveX denetimi ActiveX denetimi Sihirbazı kullanılarak oluşturulduysa bu çağrı otomatik olarak eklenir. Sürüm desteği gerekmiyorsa kaldırılabilir. Ancak, Denetim boyutu maliyeti, sürüm desteğinin sağladığı ek esneklik için çok küçüktür (4 bayt).

Denetim ActiveX Denetim Sihirbazı ile oluşturulmadıysa, `COleControl::ExchangeVersion` işlevinizin başına aşağıdaki satırı ekleyerek öğesine bir çağrı ekleyin `DoPropExchange` (çağrısından önce `COleControl::DoPropExchange` ):

[!code-cpp[NVC_MFC_AxSer#1](codesnippet/cpp/mfc-activex-controls-serializing_2.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

Sürüm numarası olarak herhangi bir **DWORD** kullanabilirsiniz. ActiveX Denetim Sihirbazı tarafından oluşturulan projeler `_wVerMinor` `_wVerMajor` Varsayılan olarak ve kullanır. Bunlar, projenin ActiveX denetim sınıfının uygulama dosyasında tanımlanan genel sabitlerdir. `DoPropExchange`İşlevinizin geri kalanında, kaydettiğiniz veya aldığınız sürümü almak için istediğiniz zaman [CPropExchange:: GetVersion](reference/cpropexchange-class.md#getversion) çağrısı yapabilirsiniz.

Aşağıdaki örnekte, bu örnek denetimin 1. sürümünde yalnızca bir "ReleaseDate" özelliği bulunur. Sürüm 2 bir "OriginalDate" özelliği ekler. Denetimin kalıcı durumu eski sürümden yüklemesi istenirse, yeni özelliğin üye değişkenini varsayılan bir değere başlatır.

[!code-cpp[NVC_MFC_AxSer#4](codesnippet/cpp/mfc-activex-controls-serializing_5.cpp)]
[!code-cpp[NVC_MFC_AxSer#3](codesnippet/cpp/mfc-activex-controls-serializing_4.cpp)]

Varsayılan olarak, bir denetim "eski verileri en son biçime dönüştürür". Örneğin, bir denetimin 2. sürümü sürüm 1 tarafından kaydedilen verileri yüklerse, yeniden kaydedildiğinde sürüm 2 biçimini yazar. Denetimin verileri son okuma biçiminde kaydetmesini istiyorsanız, çağrılırken üçüncü parametre olarak **yanlış** geçirin `ExchangeVersion` . Bu üçüncü parametre isteğe bağlıdır ve varsayılan olarak **true** 'dur.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)
