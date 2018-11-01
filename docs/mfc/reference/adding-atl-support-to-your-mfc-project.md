---
title: MFC Projenize ATL Desteği Ekleme
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.adding.atl.mfc
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: b5fe15d6-7752-4818-b9f9-62482ad35c95
ms.openlocfilehash: 9f8861e3b6aa0fee95aa84b989cf1057ae0f76b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448613"
---
# <a name="adding-atl-support-to-your-mfc-project"></a>MFC Projenize ATL Desteği Ekleme

MFC tabanlı bir uygulama oluşturduysanız, sonra Etkin Şablon kitaplığı (ATL) için destek kolayca ekleme ATL desteği için MFC proje sihirbazını çalıştırarak ekleyebilirsiniz.

> [!NOTE]
>  ATL ve MFC genellikle Visual Studio'nun Express sürümlerinde desteklenmez.

> [!NOTE]
>  Bu destek, eklenen bir MFC yürütülebilir veya DLL projesi için yalnızca basit COM nesneleri için geçerlidir. MFC projeleri (ActiveX denetimleri dahil) başka bir COM nesneleri ekleyebilirsiniz, ancak nesnelerin beklendiği gibi çalışmayabilir.

### <a name="to-add-atl-support-to-your-mfc-project"></a>MFC projenize ATL desteği eklemek için

1. Çözüm Gezgini'nde, ATL desteği eklemek istediğiniz projeye sağ tıklayın.

1. Kısayol menüsünde **Ekle**ve ardından **sınıfı Ekle**.

1. Seçin **MFC projeye ATL desteği Ekle** simgesi.

    > [!NOTE]
    >  Bu simge ATL klasöründe bulunan **kategorileri** bölmesi.

1. Sorulduğunda **Evet** ATL desteği eklenecek.

ATL desteği ekleme MFC proje kodunuzun nasıl değiştiğini hakkında daha fazla bilgi için bkz. [ayrıntıları, ATL desteği eklenen ATL Sihirbazı tarafından](../../mfc/reference/details-of-atl-support-added-by-the-atl-wizard.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Üye işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Bir sanal işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC ileti işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Sınıf yapısında gezinme](../../ide/navigating-the-class-structure-visual-cpp.md)
