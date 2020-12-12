---
description: 'Hakkında daha fazla bilgi edinin: sağlayıcınıza arabirim ekleme'
title: Sağlayıcınıza Arabirim Ekleme
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
ms.openlocfilehash: 0514f57489fd0a5d97f659fc5695cc7e0f8e03e3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246077"
---
# <a name="adding-an-interface-to-your-provider"></a>Sağlayıcınıza Arabirim Ekleme

> [!NOTE]
> ATL OLE DB sağlayıcı Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz.

Arabirimi eklemek istediğiniz nesneyi (genellikle veri kaynağı, satır kümesi, komut veya **OLE DB sağlayıcı Sihirbazı** tarafından oluşturulan oturum nesneleri) saptayın. Arabirimi eklemeniz gereken nesne, sağlayıcınızın Şu anda desteklemediği bir nesnedir. Bu durumda, nesneyi oluşturmak için **ATL OLE DB sağlayıcı Sihirbazı 'nı** çalıştırın. **Sınıf görünümü**' de projeye sağ tıklayın, menüden yeni **öğe Ekle**' ye tıklayın  >   , ATL Visual C++ **yüklü**' i seçin  >    >  ve ardından **ATL OLEDB Sağlayıcısı**' na tıklayın. Arabirim kodunu ayrı bir dizine koymak ve sonra dosyaları sağlayıcı projenize kopyalamak isteyebilirsiniz.

Arabirimini desteklemek için yeni bir sınıf oluşturduysanız, nesneyi bu sınıftan devralmasını sağlayın. Örneğin, sınıfını `IRowsetIndexImpl` bir satır kümesi nesnesine ekleyebilirsiniz:

```cpp
template <class Creator>
class CCustomRowset :
    public CRowsetImpl< CCustomRowset<Creator>, CCustomWindowsFile, Creator>,
    public IRowsetIndexImpl< ... >
```

COM_INTERFACE_ENTRY makrosunu kullanarak COM_MAP arabirimini nesnesine ekleyin. Eşleme yoksa, bir tane oluşturun. Örneğin:

```cpp
BEGIN_COM_MAP(CCustomRowset)
     COM_INTERFACE_ENTRY(IRowsetIndex)
END_COM_MAP()
```

Satır kümesi nesnesi için, nesnenin üst sınıfa temsilci seçebilmek için üst nesnesinin haritasını zincirlendirin. Bu örnekte, COM_INTERFACE_ENTRY_CHAIN makrosunu haritaya ekleyin:

```cpp
BEGIN_COM_MAP(CCustomRowset)
     COM_INTERFACE_ENTRY(IRowsetIndex)
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)
END_COM_MAP()
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonlarıyla çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)
