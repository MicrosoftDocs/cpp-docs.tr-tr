---
title: "Sağlayıcınıza arabirim ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 518cd5e67c734de48d7f021e558c7c4c3a718cdc
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="adding-an-interface-to-your-provider"></a>Sağlayıcınıza Arabirim Ekleme
Arabirim (OLE DB Sağlayıcı Sihirbazı tarafından oluşturulan genellikle veri kaynağı, satır kümesi, komut veya oturum nesneleri) için eklemek istediğiniz nesne belirler. Arabirimi eklemek için gereksinim duyduğunuz nesnenin sağlayıcınız şu anda desteklemediği olduğunu mümkündür. Bu durumda, ATL OLE DB sağlayıcısı nesneyi oluşturmak için sihirbazı çalıştırın. Sınıf Görünümü'nde projeye sağ tıklayın, **sınıfı Ekle** gelen **Ekle** menüsüne ve ardından **ATL OLE DB sağlayıcısı**. Arabirim kodunu ayrı bir klasöre yerleştirin ve ardından dosyaları sağlayıcı projenize kopyalamak isteyebilirsiniz.  
  
 Arabirimi desteklemek için yeni bir sınıf oluşturduysanız, bu sınıftan nesnesini yapın. Örneğin, sınıf ekleme olasılığınız **IRowsetIndexImpl** bir satır kümesi nesnesi için:  
  
```cpp  
template <class Creator>  
class CAgentRowset :   
    public CRowsetImpl< CAgentRowset<Creator>, CAgentMan, Creator>,  
    public IRowsetIndexImpl< ... >   
```  
  
 Arabirim ekleme **COM_MAP** COM_INTERFACE_ENTRY makrosu kullanarak nesnesindeki. Eşleme yok ise, bir tane oluşturun. Örneğin:  
  
```cpp  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
END_COM_MAP()  
```  
  
 Satır kümesi nesnesi için zinciri harita kendi üst nesne için üst sınıf devredebilirsiniz böylece nesne. Bu örnekte, COM_INTERFACE_ENTRY_CHAIN makrosu eşlemeye ekleyin:  
  
```cpp  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)  
END_COM_MAP()  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)