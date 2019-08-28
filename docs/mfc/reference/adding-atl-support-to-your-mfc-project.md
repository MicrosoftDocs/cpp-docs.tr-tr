---
title: MFC Projenize ATL Desteği Ekleme
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.adding.atl.mfc
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: b5fe15d6-7752-4818-b9f9-62482ad35c95
ms.openlocfilehash: fba79db013cd9f4cc62ba5826b53e5fa9b15c83a
ms.sourcegitcommit: bf1940a39029dbbd861f95480f55e5e8bd25cda0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/28/2019
ms.locfileid: "70108411"
---
# <a name="adding-atl-support-to-your-mfc-project"></a>MFC Projenize ATL Desteği Ekleme

Zaten bir MFC tabanlı uygulama oluşturduysanız, IDE 'yi kullanarak etkin şablon kitaplığı (ATL) için destek ekleyebilirsiniz.

> [!NOTE]
>  Bu destek yalnızca MFC yürütülebilir dosyası veya DLL projesine eklenen basit COM nesneleri için geçerlidir. MFC projelerine başka COM nesneleri (ActiveX denetimleri dahil) ekleyebilirsiniz, ancak nesneler beklendiği gibi çalışmayabilir.

::: moniker range=">=vs-2019"

1. Çözüm Gezgini, proje düğümüne sağ tıklayın.

1. Kısayol menüsünde, **Ekle**' ye ve ardından **Yeni öğe**' ye tıklayın.

1. Sol bölmede **ATL** ' yi seçin ve ardından orta bölmedeki **atl desteği** ' ni seçin.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-add-atl-support-to-your-mfc-project"></a>MFC projenize ATL desteği eklemek için

1. Çözüm Gezgini, proje düğümüne sağ tıklayın.

1. Kısayol menüsünde, **Ekle**' ye ve ardından **Sınıf Ekle**' ye tıklayın.

1. Sol bölmede **ATL** ' yi seçin ve ardından orta bölmedeki **MFC projesine atl desteği ekle** ' yi seçin.

::: moniker-end

ATL desteğinin nasıl eklendiği hakkında daha fazla bilgi için, bkz [. ATL Sihirbazı tarafından eklenen ATL desteğinin ayrıntıları](../../mfc/reference/details-of-atl-support-added-by-the-atl-wizard.md)

## <a name="see-also"></a>Ayrıca bkz.

[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Üye Işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Sanal Işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Ileti Işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Sınıf yapısında gezinme](../../ide/navigate-code-cpp.md)
