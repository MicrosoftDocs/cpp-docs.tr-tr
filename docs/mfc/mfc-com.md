---
title: MFC COM | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MFC COM (MFC)
dev_langs:
- C++
helpviewer_keywords:
- MFC, COM support
- MFC ActiveX controls [MFC], COM support in MFC
- MFC COM [MFC]
- ActiveX controls [MFC], COM object model
- Active technology [MFC]
- COM [MFC], MFC support
ms.assetid: 7646bdcb-3a06-4ed5-9386-9b00f3979dcb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ae1ccdcda4fac1cbd0660b054d792999ae449fc
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50079295"
---
# <a name="mfc-com"></a>MFC COM

MFC bir alt kümesi, en etkin Şablon kitaplığı (ATL), tasarlanmış olmasına rağmen COM'u desteklemek üzere tasarlanmıştır COM programlama için. Bu bölümde konu com için MFC'nin desteğini açıklar.

(Örneğin, ActiveX denetimleri, etkin belge kapsaması, OLE ve benzeri) etkin teknolojileri, ağ ortamında, oldukları diline bakılmaksızın birbiriyle etkileşim kurmak yazılım bileşenlerini etkinleştirmek için Bileşen Nesne Modeli (COM) kullanın. oluşturuldu. Etkin teknoloji, masaüstü veya Internet üzerinde çalışan uygulamalar oluşturmak için kullanılabilir. Daha fazla bilgi için [COM'a giriş](../atl/introduction-to-com.md) veya [Bileşen Nesne modeli](/windows/desktop/com/the-component-object-model).

Etkin teknoloji, aşağıdakiler dahil olmak üzere, istemci ve sunucu teknolojileri şunları içerir:

- ActiveX denetimleri, bir Web sitesi gibi kapsayıcılar kullanılabilir etkileşimli nesnelerdir. ActiveX denetimleri hakkında daha fazla bilgi için bkz:

   - [MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

   - [Internet'te ActiveX Denetimleri](../mfc/activex-controls-on-the-internet.md)

   - [Genel Bakış: Internet](../mfc/mfc-internet-programming-basics.md)

   - [Internet'te kullanılacak varolan bir ActiveX denetimini yükseltme](../mfc/upgrading-an-existing-activex-control.md)

   - [ActiveX denetimi hata ayıklama](/visualstudio/debugger/how-to-debug-an-activex-control)

- Etkin komut dosyası, tarayıcı veya sunucu bir veya daha fazla ActiveX denetimlerini tümleşik davranışını denetler. Etkin komut dosyası oluşturma hakkında daha fazla bilgi için bkz. [Internet'te etkin teknoloji](../mfc/active-technology-on-the-internet.md).

- [Otomasyon](../mfc/automation.md) (eski adıyla OLE Otomasyonu da bilinir), bir uygulama için başka bir uygulamaya uygulanan nesneleri değiştirmek ya da "bunlar işlenebilir nesneleri göstermek için" mümkün kılar.

   Otomatik nesne yerel veya uzak (başka bir makinedeki bir ağ üzerinden erişilebilir) olabilir. Otomasyon OLE hem COM nesneleri için kullanılabilir.

- Bu bölümde, MFC, örneğin kullanarak COM bileşenlerini yazmaya yönelik bilgi de sağlar. [bağlantı noktaları](../mfc/connection-points.md).

Ne artık etkin teknoloji adı verilir ve hangi OLE yine de çağrılır, bir açıklaması için üzerinde konulara bakın. [OLE](../mfc/ole-in-mfc.md).

## <a name="in-this-section"></a>Bu Bölümde

[Etkin Belge Kapsaması](../mfc/active-document-containment.md)

[Otomatikleştirme](../mfc/automation.md)

[Bağlantı Noktaları](../mfc/connection-points.md)

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Kavramları](../mfc/mfc-concepts.md)

