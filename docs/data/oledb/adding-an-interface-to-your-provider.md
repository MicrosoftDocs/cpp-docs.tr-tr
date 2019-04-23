---
title: Sağlayıcınıza Arabirim Ekleme
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
ms.openlocfilehash: c0452ca74509b65de3787af93bff41b3cb399c99
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033884"
---
# <a name="adding-an-interface-to-your-provider"></a>Sağlayıcınıza Arabirim Ekleme

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