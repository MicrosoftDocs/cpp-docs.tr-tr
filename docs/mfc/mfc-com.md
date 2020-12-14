---
description: 'Daha fazla bilgi edinin: MFC COM'
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
ms.openlocfilehash: a7f4387aa692eb0610052f85870127ac54761437
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280670"
---
# <a name="mfc-com"></a>MFC COM

MFC 'nin bir alt kümesi COM desteği için tasarlanmıştır, ancak etkin şablon kitaplığı (ATL) çoğu COM programlama için tasarlanmıştır. Konuların bu bölümü, MFC 'nin COM desteğini açıklar.

Etkin teknolojiler (ActiveX denetimleri, etkin belge kapsamı, OLE vb.), yazılım bileşenlerinin oluşturuldukları dilden bağımsız olarak, ağa bağlı bir ortamda etkileşime geçmesini sağlamak için bileşen nesne modeli 'ni (COM) kullanır. Etkin teknolojiler masaüstü veya Internet üzerinde çalışan uygulamalar oluşturmak için kullanılabilir. Daha fazla bilgi için bkz. COM veya [bileşen nesne modeline](/windows/win32/com/the-component-object-model) [giriş](../atl/introduction-to-com.md) .

Etkin teknolojiler, aşağıdakiler de dahil olmak üzere hem istemci hem de sunucu teknolojilerini içerir:

- ActiveX denetimleri, Web sitesi gibi kapsayıcılarında kullanılabilen etkileşimli nesnelerdir. ActiveX denetimleri hakkında daha fazla bilgi için bkz.

  - [MFC ActiveX denetimleri](mfc-activex-controls.md)

  - [Internet 'te ActiveX denetimleri](activex-controls-on-the-internet.md)

  - [Genel Bakış: Internet](mfc-internet-programming-basics.md)

  - [Internet 'te kullanılacak mevcut bir ActiveX denetimini yükseltme](upgrading-an-existing-activex-control.md)

  - [ActiveX denetiminde hata ayıklama](/visualstudio/debugger/how-to-debug-an-activex-control)

- Etkin betik bir tarayıcıdan veya sunucudan bir veya daha fazla ActiveX denetiminin tümleşik davranışını denetler. Etkin betik oluşturma hakkında daha fazla bilgi için bkz. [Internet üzerinde etkin teknoloji](active-technology-on-the-internet.md).

- [Otomasyon](automation.md) (eskı adıyla OLE Otomasyonu), bir uygulamanın başka bir uygulamada uygulanan nesneleri işlemesini veya işlenebilmeleri için nesneleri "kullanıma sunmayı" sağlar.

   Otomatik nesne yerel veya uzak olabilir (ağ üzerinden erişilebilen başka bir makineye). Otomasyon hem OLE hem de COM nesneleri için kullanılabilir.

- Bu bölüm ayrıca, örneğin [bağlantı NOKTALARıNDA](connection-points.md)MFC kullanarak com bileşenlerini yazma hakkında bilgi sağlar.

Hala OLE olarak adlandırıldığına ve artık etkin teknolojinin ne olduğuna ilişkin bir tartışma için, [OLE](ole-in-mfc.md)'deki konulara bakın.

## <a name="in-this-section"></a>Bu Bölümde

[Etkin belge kapsama](active-document-containment.md)

[Otomasyon](automation.md)

[Bağlantı noktaları](connection-points.md)

[MFC ActiveX denetimleri](mfc-activex-controls.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](mfc-concepts.md)
