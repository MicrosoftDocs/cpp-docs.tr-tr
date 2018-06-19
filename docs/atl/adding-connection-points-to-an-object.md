---
title: Bağlantı noktaları için bir nesne ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], adding to ATL objects
- Implement Connection Point ATL wizard
ms.assetid: 843531be-4a36-4db0-9d54-e029b1a72a8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71f9d136ccdeded02303894195c7b8126acafd9c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356598"
---
# <a name="adding-connection-points-to-an-object"></a>Bağlantı noktaları için bir nesne ekleme
[ATL öğretici](../atl/active-template-library-atl-tutorial.md) bir denetimin bağlantı noktaları için destek ile nasıl oluşturulacağını, olaylar ekleme ve sonra bağlantı noktası uygulamak nasıl gösterilir. ATL bağlantı noktaları ile uygulayan [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) sınıfı.  
  
 Bir bağlantı noktası uygulamak için iki seçeneğiniz vardır:  
  
-   Giden kendi olay kaynağı, bir bağlantı noktası denetim veya nesnenin ekleyerek uygulayın.  
  
-   Başka bir tür kitaplığı'nda tanımlanan bir bağlantı noktası arabirimi yeniden kullanabilirsiniz.  
  
 Her iki durumda da, bağlantı noktası uygulama sihirbazı işini yapmak için bir tür kitaplığı kullanır.  
  
### <a name="to-add-a-connection-point-to-a-control-or-object"></a>Bir denetim veya nesne için bir bağlantı noktası eklemek için  
  
1.  Bir görüntüleme arabirimi .idl dosya kitaplığını bloğunu tanımlayın. ATL Denetim Sihirbazı'yla denetimi oluşturduğunuzda bağlantı noktaları için destek etkinleştirilirse, görüntüleme arabirimi zaten oluşturulur. Denetim oluşturduğunuzda bağlantı noktaları için destek etkinleştirmediyseniz, bir görüntüleme arabirimi .idl dosyasına el ile eklemeniz gerekir. Bir görüntüleme arabirimi örneği verilmiştir. Giden arabirimleri gönderme arabirimleri olması gerekli değildir ancak bu, bu örnek iki dispinterfaces kullanan VBScript ve JScript gibi pek çok komut dosyası dilleri gerektirir:  
  
     [!code-cpp[NVC_ATL_Windowing#81](../atl/codesnippet/cpp/adding-connection-points-to-an-object_1.idl)]  
  
     Bir GUID oluşturmak için uuidgen.exe veya guidgen.exe yardımcı programını kullanın.  
  
2.  Görüntüleme arabirimi olarak ekleme `[default,source]` projenin .idl dosyasını nesnesinde coclass'ı arabiriminde. ATL Denetim Sihirbazı'nı denetim oluşturduğunuzda bağlantı noktaları için destek etkinleştirilirse, yeniden oluşturacak `[default,source`] girişi. Bu girdi el ile eklemek için satırı kalın ekleyin:  
  
     [!code-cpp[NVC_ATL_Windowing#82](../atl/codesnippet/cpp/adding-connection-points-to-an-object_2.idl)]  
  
     .İdl dosyasında bkz [Dai](../visual-cpp-samples.md) ATL örnek olarak.  
  
3.  Sınıf Görünümü olay arabirim yöntemleri ve özellikleri eklemek için kullanın. Sınıf Görünümü sınıfında sağ tıklayın, fareyle **Ekle** kısayol menüsüne ve ardından üzerinde **bağlantı noktası ekleme**.  
  
4.  İçinde **kaynak arabirimleri** bağlantı noktası Uygulama Sihirbazı, select liste kutusunda **projenin arabirimleri**. Denetim ve ENTER tuşuna basın bir arabirim seçerseniz **Tamam**, şunları yapacaksınız:  
  
    -   Olayı için giden aramaları yapmadan kodu uygulayan bir olay proxy sınıfı ile üstbilgi dosyası oluşturur.  
  
    -   Bir girdi için bağlantı noktası eşlemesi ekleyin.  
  
     Ayrıca, bilgisayarınızda tüm türü kitaplıkların listesini görürsünüz. Yalnızca bu diğer tür kitaplıklarından birini başka bir tür kitaplığı'nda bulunan tam aynı giden arabirimi uygulamak istiyorsanız, bağlantı noktası tanımlamak için kullanmanız gerekir.  
  
### <a name="to-reuse-a-connection-point-interface-defined-in-another-type-library"></a>Bir bağlantı noktası arabirimi yeniden kullanmak için başka bir tür kitaplığı'nda tanımlanan  
  
1.  Sınıf Görünümü'nde uygulayan bir sınıf sağ bir **BEGIN_COM_MAP** makrosu, noktasına **Ekle** kısayol menüsüne ve ardından üzerinde **bağlantı noktası ekleme**.  
  
2.  Bağlantı noktası Uygulama Sihirbazı, bir tür kitaplığı ve arabirim olarak tür kitaplığını seçin ve'ı tıklatın **Ekle**.  
  
3.  Ya da .idl dosyasını düzenleyin:  
  
    -   Olay kaynağı kullanılan nesne .idl dosyasındaki görüntüleme arabirimi kopyalayın.  
  
    -   Kullanım **importlib** bu tür kitaplığı yönerge.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlantı noktası](../atl/atl-connection-points.md)

