---
title: ATL OLE DB Tüketicisi Ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
- OLE DB, adding ATL OLE DB consumer to projects
- ATL OLE DB consumers
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90b16c84c0dc2c921722c4c80a1e2bdf0e091d9c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="adding-an-atl-ole-db-consumer"></a>ATL OLE DB Tüketicisi Ekleme
ATL OLE DB tüketici bir projeye eklemek için bu sihirbazı kullanın. ATL OLE DB tüketici bir OLE DB erişimcisi sınıf ve veri bağlamalarını bir veri kaynağına erişmek için gerekli oluşur. Proje ATL COM uygulama olarak ya da (ATL OLE DB Tüketici Sihirbazı otomatik olarak ekler) ATL desteği içeren bir MFC ya da Win32 uygulama olarak oluşturulmuş olması gerekir.  
  
 **Not** bir MFC projesine bir OLE DB Tüketicisi ekleyebilirsiniz. Bunu yaparsanız, ATL OLE DB Tüketici Sihirbazı projenize gerekli COM desteği ekler. Bu MFC projesi oluşturduğunuzda, seçtiğiniz varsayar **ActiveX denetimlerini** onay kutusunu (içinde **Gelişmiş Özellikler** MFC projesi Uygulama Sihirbazı sayfasında), varsayılan olarak işaretli. Bu seçeneğin belirlenmesi sağlar uygulama çağırır **CoInitialize** ve **CoUninitialize**. Seçmediyseniz, **ActiveX denetimlerini** MFC projesi oluşturduğunuzda, çağırmanız gerekir **CoInitialize** ve **CoUninitialize** ana kodunuzda.  
  
### <a name="to-add-an-atl-ole-db-consumer-to-your-project"></a>ATL OLE DB Tüketici projenize eklemek için  
  
1.  Sınıf Görünümü'nde projeye sağ tıklayın. Kısayol menüsünde **Ekle** ve ardından **sınıfı Ekle**.  
  
2.  Visual C++ klasörünü çift tıklatarak **ATL OLE DB Tüketicisi** simgesini seçin veya tıklatın **açık**.  
  
     ATL OLE DB Tüketici Sihirbazı açılır.  
  
3.  Bölümünde açıklandığı gibi ayarlarını tanımla [ATL OLE DB Tüketici Sihirbazı](../../atl/reference/atl-ole-db-consumer-wizard.md).  
  
4.  Tıklatın **son** sihirbazı kapatın. Yeni oluşturulan OLE DB Tüketici kod projenize eklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)

