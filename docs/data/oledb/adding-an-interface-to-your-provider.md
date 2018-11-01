---
title: Sağlayıcınıza Arabirim Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
ms.openlocfilehash: 295a7955b78918d6281a28b616f201869f37b01e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488679"
---
# <a name="adding-an-interface-to-your-provider"></a>Sağlayıcınıza Arabirim Ekleme

(OLE DB sağlayıcısı Sihirbazı tarafından oluşturulan genellikle veri kaynağı, satır kümesi, komut veya oturum nesneleri) arabirim eklemek istediğiniz nesneyi belirleyin. Eklemek istediğiniz nesne sağlayıcınız şu anda desteklemediği bir olduğunu mümkündür. Bu durumda, ATL OLE DB sağlayıcısı nesneyi oluşturmak için sihirbazı çalıştırın. Sınıf Görünümü'nde projeye sağ tıklayın, **sınıfı Ekle** gelen **Ekle** menüsüne ve ardından **ATL OLE DB sağlayıcısı**. Arabirimi kodunu ayrı bir klasöre yerleştirin ve ardından dosyaları sağlayıcısı projenize kopyalayın isteyebilirsiniz.

Arabirimi desteklemek için yeni bir sınıf oluşturduysanız, bu sınıftan nesne olun. Örneğin, sınıf ekleyebilirsiniz **IRowsetIndexImpl** satır kümesi nesnesi için:

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

Satır kümesi nesnesi için zinciri üst haritasını böylece nesnenin üst sınıf devredebilirsiniz nesne. Bu örnekte, haritayı COM_INTERFACE_ENTRY_CHAIN makro ekleyin:

```cpp
BEGIN_COM_MAP(CAgentRowset)
     COM_INTERFACE_ENTRY(IRowsetIndex)
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)
END_COM_MAP()
```

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)