---
description: 'Daha fazla bilgi edinin: ATL OLE DB tüketicisi ekleme'
title: ATL OLE DB Tüketicisi Ekleme
ms.date: 05/09/2019
helpviewer_keywords:
- ATL OLE DB consumers
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
ms.openlocfilehash: cfd88524e369781b239bb0246ab59fcf0080a144
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159108"
---
# <a name="adding-an-atl-ole-db-consumer"></a>ATL OLE DB Tüketicisi Ekleme

::: moniker range="msvc-160"

ATL OLE DB Tüketici Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. İşlevselliği el ile de ekleyebilirsiniz. Daha fazla bilgi için bkz. [Sihirbaz kullanmadan tüketici oluşturma](../../data/oledb/creating-a-consumer-without-using-a-wizard.md).

::: moniker-end

::: moniker range="<=msvc-150"

Bir projeye ATL OLE DB tüketicisi eklemek için bu sihirbazı kullanın. ATL OLE DB tüketicisi, bir veri kaynağına erişmek için gereken OLE DB erişimci sınıfından ve veri bağlamalarından oluşur. Projenin bir ATL COM uygulaması veya ATL desteği içeren bir MFC ya da Win32 uygulaması olarak oluşturulmuş olması gerekir (ATL OLE DB Tüketici Sihirbazı otomatik olarak eklenir).

> [!NOTE]
> Bir MFC projesine OLE DB tüketicisini ekleyebilirsiniz. Bunu yaparsanız, ATL OLE DB Tüketici Sihirbazı projenize gerekli COM desteğini ekler. Bu, MFC projesini oluşturduğunuz zaman, varsayılan olarak denetlenen **ActiveX denetimleri** onay kutusunu (MFC Proje uygulaması sihirbazının **Gelişmiş Özellikler** sayfasında) seçtiğinizi kabul eder. Bu seçeneğin belirlenmesi, uygulamanın ve çağrısı yapılmasını `CoInitialize` sağlar `CoUninitialize` . MFC projesini oluştururken **ActiveX denetimlerini** seçmediyseniz, `CoInitialize` Ana kodunuzda ve çağırmanız gerekir `CoUninitialize` .

## <a name="to-add-an-atl-ole-db-consumer-to-your-project"></a>Projenize ATL OLE DB tüketicisi eklemek için

1. **Sınıf görünümü**, projeye sağ tıklayın. Kısayol menüsünde, **Ekle** ' ye ve ardından **Sınıf Ekle**' ye tıklayın.

1. Visual C++ klasöründe, **ATL OLE DB tüketicisi** simgesine çift tıklayın veya seçin ve **Aç**' a tıklayın.

   ATL OLE DB Tüketici Sihirbazı açılır.

1. [ATL OLE DB Tüketici Sihirbazı](../../atl/reference/atl-ole-db-consumer-wizard.md)'nda açıklanan ayarları tanımlayın.

1. Sihirbazı kapatmak için **son** ' a tıklayın. Yeni oluşturulan OLE DB tüketici kodu projenize eklenecektir.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)
