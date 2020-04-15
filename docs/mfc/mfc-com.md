---
title: MFC COM
ms.date: 09/12/2018
f1_keywords:
- MFC COM (MFC)
helpviewer_keywords:
- MFC, COM support
- MFC ActiveX controls [MFC], COM support in MFC
- MFC COM [MFC]
- ActiveX controls [MFC], COM object model
- Active technology [MFC]
- COM [MFC], MFC support
ms.assetid: 7646bdcb-3a06-4ed5-9386-9b00f3979dcb
ms.openlocfilehash: 514251475050e728be1959417ead1dbdf96e4800
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358189"
---
# <a name="mfc-com"></a>MFC COM

MFC'nin bir alt kümesi COM'u desteklemek üzere tasarlanırken, Etkin Şablon Kitaplığı'nın (ATL) çoğu COM programlaması için tasarlanmıştır. Konuların bu bölümünde MFC'nin COM desteği açıklanmaktadır.

Etkin teknolojiler (ActiveX denetimleri, Etkin belge kapsama, OLE vb. gibi) yazılım bileşenlerinin oluşturuldukları dilden bağımsız olarak ağ ortamında birbirleriyle etkileşimedebilmelerini sağlamak için Bileşen Nesne Modeli'ni (COM) kullanır. Etkin teknolojiler masaüstünde veya Internet'te çalışan uygulamalar oluşturmak için kullanılabilir. Daha fazla bilgi için [The Component Object Model](/windows/win32/com/the-component-object-model) [bkz.](../atl/introduction-to-com.md)

Etkin teknolojiler, aşağıdakiler de dahil olmak üzere hem istemci hem de sunucu teknolojilerini içerir:

- ActiveX denetimleri, Web sitesi gibi kapsayıcılarda kullanılabilecek etkileşimli nesnelerdir. ActiveX denetimleri hakkında daha fazla bilgi için bkz:

  - [MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)

  - [Internet'te ActiveX Denetimleri](../mfc/activex-controls-on-the-internet.md)

  - [Genel Bakış: İnternet](../mfc/mfc-internet-programming-basics.md)

  - [Internet'te Kullanılmak Üzere Varolan ActiveX Denetimini Yükseltme](../mfc/upgrading-an-existing-activex-control.md)

  - [ActiveX Denetiminin Hata Ayıklanması](/visualstudio/debugger/how-to-debug-an-activex-control)

- Etkin komut dosyası, bir tarayıcıveya sunucudan bir veya daha fazla ActiveX denetiminin tümleşik davranışını denetler. Etkin komut dosyası hakkında daha fazla bilgi için [Internet'te Etkin Teknoloji'ye](../mfc/active-technology-on-the-internet.md)bakın.

- [Otomasyon](../mfc/automation.md) (eski adıyla OLE Automation), bir uygulamanın başka bir uygulamada uygulanan nesneleri işlemesini veya nesneleri manipüle edilebilmeleri için "açığa çıkarmasını" mümkün kılar.

   Otomatik nesne yerel veya uzak olabilir (ağ üzerinden erişilebilen başka bir makinede). Otomasyon hem OLE hem de COM nesneleri için kullanılabilir.

- Bu bölümde [ayrıca, Örneğin Bağlantı Noktaları'nda](../mfc/connection-points.md)MFC kullanarak COM bileşenlerinin nasıl yazılabağlanakadar yazılabilenler hakkında bilgi de verilmektedir.

Hala OLE ve şimdi aktif teknoloji olarak adlandırılan ne denir bir tartışma için, [OLE](../mfc/ole-in-mfc.md)konulara bakın.

## <a name="in-this-section"></a>Bu Bölümde

[Etkin Belge İçerme](../mfc/active-document-containment.md)

[Otomasyon](../mfc/automation.md)

[Bağlantı Noktaları](../mfc/connection-points.md)

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../mfc/mfc-concepts.md)
