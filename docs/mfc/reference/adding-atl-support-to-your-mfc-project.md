---
description: 'Hakkında daha fazla bilgi edinin: MFC projenize ATL desteği ekleme'
title: MFC Projenize ATL Desteği Ekleme
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.adding.atl.mfc
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: b5fe15d6-7752-4818-b9f9-62482ad35c95
ms.openlocfilehash: 1d02bd6e63a01334fcb9a907dc9ea4fe78ff4a48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248248"
---
# <a name="adding-atl-support-to-your-mfc-project"></a>MFC Projenize ATL Desteği Ekleme

Zaten bir MFC tabanlı uygulama oluşturduysanız, IDE 'yi kullanarak etkin şablon kitaplığı (ATL) için destek ekleyebilirsiniz.

> [!NOTE]
> Bu destek yalnızca MFC yürütülebilir dosyası veya DLL projesine eklenen basit COM nesneleri için geçerlidir. MFC projelerine başka COM nesneleri (ActiveX denetimleri dahil) ekleyebilirsiniz, ancak nesneler beklendiği gibi çalışmayabilir.

::: moniker range=">=msvc-160"

1. Çözüm Gezgini, proje düğümüne sağ tıklayın.

1. Kısayol menüsünde, **Ekle**' ye ve ardından **Yeni öğe**' ye tıklayın.

1. Sol bölmede **ATL** ' yi seçin ve ardından orta bölmedeki **atl desteği** ' ni seçin.

::: moniker-end

::: moniker range="<=msvc-150"

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
