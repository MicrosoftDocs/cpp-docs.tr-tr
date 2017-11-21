---
title: "Sağlayıcınıza arabirim ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a9a5a383e32a4fa5cb626dee499d5b2262abe37c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="adding-an-interface-to-your-provider"></a>Sağlayıcınıza Arabirim Ekleme
Arabirim (OLE DB Sağlayıcı Sihirbazı tarafından oluşturulan genellikle veri kaynağı, satır kümesi, komut veya oturum nesneleri) için eklemek istediğiniz nesne belirler. Arabirimi eklemek için gereksinim duyduğunuz nesnenin sağlayıcınız şu anda desteklemediği olduğunu mümkündür. Bu durumda, ATL OLE DB sağlayıcısı nesneyi oluşturmak için sihirbazı çalıştırın. Sınıf Görünümü'nde projeye sağ tıklayın, **sınıfı Ekle** gelen **Ekle** menüsüne ve ardından **ATL OLE DB sağlayıcısı**. Arabirim kodunu ayrı bir klasöre yerleştirin ve ardından dosyaları sağlayıcı projenize kopyalamak isteyebilirsiniz.  
  
 Arabirimi desteklemek için yeni bir sınıf oluşturduysanız, bu sınıftan nesnesini yapın. Örneğin, sınıf ekleme olasılığınız **IRowsetIndexImpl** bir satır kümesi nesnesi için:  
  
```  
template <class Creator>  
class CAgentRowset :   
public CRowsetImpl< CAgentRowset<Creator>, CAgentMan, Creator>,  
   public IRowsetIndexImpl< ... >   
```  
  
 Arabirim ekleme **COM_MAP** COM_INTERFACE_ENTRY makrosu kullanarak nesnesindeki. Eşleme yok ise, bir tane oluşturun. Örneğin:  
  
```  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
END_COM_MAP()  
```  
  
 Satır kümesi nesnesi için zinciri harita kendi üst nesne için üst sınıf devredebilirsiniz böylece nesne. Bu örnekte, COM_INTERFACE_ENTRY_CHAIN makrosu eşlemeye ekleyin:  
  
```  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)  
END_COM_MAP()  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)