---
title: MFC Projenize ATL Desteği Ekleme
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.adding.atl.mfc
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: b5fe15d6-7752-4818-b9f9-62482ad35c95
ms.openlocfilehash: 05c4e8ba54d9a573b422f136c9e8cf69e48d1c9a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371679"
---
# <a name="adding-atl-support-to-your-mfc-project"></a>MFC Projenize ATL Desteği Ekleme

MFC tabanlı bir uygulama oluşturduysanız, IDE'yi kullanarak Etkin Şablon Kitaplığı (ATL) için destek ekleyebilirsiniz.

> [!NOTE]
> Bu destek yalnızca bir MFC çalıştırılabilir veya DLL projesine eklenen basit COM nesneleri için geçerlidir. MFC projelerine diğer COM nesnelerini (ActiveX denetimleri dahil) ekleyebilirsiniz, ancak nesneler beklendiği gibi çalışmayabilir.

::: moniker range=">=vs-2019"

1. Çözüm Gezgini'nde proje düğümüne sağ tıklayın.

1. Kısayol menüsünde **Ekle'yi**tıklatın ve ardından **Yeni Öğe'yi**tıklatın.

1. Sol bölmede **ATL'yi** seçin ve ardından orta bölmede **ATL Desteği'ni** seçin.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-add-atl-support-to-your-mfc-project"></a>MFC projenize ATL desteği eklemek için

1. Çözüm Gezgini'nde proje düğümüne sağ tıklayın.

1. Kısayol menüsünde **Ekle'yi**tıklatın ve sonra **Sınıf Ekle'yi**tıklatın.

1. Sol bölmede **ATL'yi** seçin ve ardından orta bölmede **MFC Projesi'ne ATL Desteği Ekle'yi** seçin.

::: moniker-end

ATL desteği eklemenin MFC projenizin kodunu nasıl değiştirdiği hakkında daha fazla bilgi için, [ATL Sihirbazı tarafından eklenen ATL Desteğinin Ayrıntıları'na](../../mfc/reference/details-of-atl-support-added-by-the-atl-wizard.md) bakın

## <a name="see-also"></a>Ayrıca bkz.

[Sınıf Ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Üye İşlev Ekleme](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Üye Değişkeni Ekleme](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Sanal İşlev Geçersiz Kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC İleti Işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Sınıf Yapısında Gezinme](../../ide/navigate-code-cpp.md)
