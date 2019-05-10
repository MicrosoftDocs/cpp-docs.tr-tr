---
title: Sağlayıcınıza Arabirim Ekleme
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
ms.openlocfilehash: a1d219568c1787558674c47edd55436b8690a61c
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2019
ms.locfileid: "65524803"
---
# <a name="adding-an-interface-to-your-provider"></a>Sağlayıcınıza Arabirim Ekleme

> [!NOTE]
> ATL OLE DB sağlayıcısı Sihirbazı'nı ve sonrasında Visual Studio 2019 içinde kullanılabilir değil.

Hangi arabirimi eklemek istediğiniz nesne belirler (genellikle veri kaynağı, satır kümesi, komut veya oturum nesneleri tarafından oluşturulan **OLE DB sağlayıcısı Sihirbazı**). Eklemek istediğiniz nesne sağlayıcınız şu anda desteklemediği bir olduğunu mümkündür. Bu durumda, çalıştırma **ATL OLE DB sağlayıcısı Sihirbazı** nesnesi oluşturulamıyor. Projeye sağ **sınıf görünümü**, tıklayın **Ekle** > **yeni öğe** menüden **yüklü**  >  **Visual C++** > **ATL**ve ardından **ATL OLEDB Sağlayıcısı**. Arabirimi kodunu ayrı bir klasöre yerleştirin ve ardından dosyaları sağlayıcısı projenize kopyalayın isteyebilirsiniz.

Arabirimi desteklemek için yeni bir sınıf oluşturduysanız, bu sınıftan nesne olun. Örneğin, sınıf ekleyebilirsiniz `IRowsetIndexImpl` satır kümesi nesnesi için:

```cpp
template <class Creator>
class CCustomRowset :
    public CRowsetImpl< CCustomRowset<Creator>, CCustomWindowsFile, Creator>,
    public IRowsetIndexImpl< ... >
```

Arabirim COM_MAP COM_INTERFACE_ENTRY makrosu kullanarak nesneyi ekleyin. Eşleme yok ise, bir tane oluşturun. Örneğin:

```cpp
BEGIN_COM_MAP(CCustomRowset)
     COM_INTERFACE_ENTRY(IRowsetIndex)
END_COM_MAP()
```

Satır kümesi nesnesi için zinciri üst haritasını böylece nesnenin üst sınıf devredebilirsiniz nesne. Bu örnekte, haritayı COM_INTERFACE_ENTRY_CHAIN makro ekleyin:

```cpp
BEGIN_COM_MAP(CCustomRowset)
     COM_INTERFACE_ENTRY(IRowsetIndex)
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)
END_COM_MAP()
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)