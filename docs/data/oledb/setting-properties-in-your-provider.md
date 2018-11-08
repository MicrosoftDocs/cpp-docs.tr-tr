---
title: Sağlayıcınızdaki Özellikleri Ayarlama
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB providers, properties
- properties [C++], OLE DB provider
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
ms.openlocfilehash: 8dfe69bd50918a9098e612cad892f1d832acb665
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2018
ms.locfileid: "51264911"
---
# <a name="setting-properties-in-your-provider"></a>Sağlayıcınızdaki Özellikleri Ayarlama

Özellik kimliği ve özellik grubu istediğiniz özelliği bulun. Daha fazla bilgi için [OLE DB özellikleri](/previous-versions/windows/desktop/ms722734) içinde **OLE DB Programcının Başvurusu**.

Sihirbaz tarafından oluşturulan sağlayıcısı, özellik grubuna karşılık gelen özellik eşlemesi bulun. Özellik grubu adını, genellikle nesnenin adına karşılık gelir. Komut ve satır kümesi özellikleri, komut veya satır kümesi bulunabilir. veri kaynağı ve başlatma özellikleri veri kaynağı nesnesi içinde bulunabilir.

Özellik eşlemesinde ekleme bir [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md) makrosu. PROPERTY_INFO_ENTRY_EX dört parametre alır:

- Özelliğine karşılık gelen özellik kimliği. Özellik adı önünden önce yedi karakterini ("DBPROP_") kaldırın. Örneğin, eklemek istediğiniz `DBPROP_MAXROWS`, geçmesi `MAXROWS` ilk öğesi olarak. Özel bir özellik varsa, GUID tam adını geçirin (örneğin, `DBMYPROP_MYPROPERTY`).

- Değişken türü özelliğinin (içinde [OLE DB özellikleri](/previous-versions/windows/desktop/ms722734) içinde **OLE DB Programcının Başvurusu**). VT_ türlerinin (örneğin, VT_BOOL veya VT_I2) veri türüne ilişkin girin.

- Özelliği okunabilir ve yazılabilir olup olmadığı ve ait olduğu grubu belirtmek için bayrakları. Örneğin, aşağıdaki kod satır grubuna ait bir okuma/yazma özelliği gösterir:

    ```cpp
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE
    ```

- Özelliğin taban değeri. Bu olabilir `VARIANT_FALSE` için bir Boole değeri yazın veya örneğin bir tamsayı türü için sıfır. Özelliği, değişmediği sürece bu değere sahip.

    > [!NOTE]
    > Bazı özellikler bağlı veya yer işaretleri veya güncelleştirme gibi diğer özelliklere zincirleme. Bir tüketici bir özelliği true olarak ayarlar, başka bir özellik de ayarlanması gerekir. OLE DB sağlayıcı şablonları bu yöntemi aracılığıyla destek [CUtlProps::OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md).

## <a name="properties-ignored-by-microsoft-ole-db-providers"></a>Microsoft OLE DB sağlayıcıları tarafından göz ardı özellikleri

OLE DB aşağıdakiler Microsoft OLE DB sağlayıcıları yoksay:

- `DBPROP_MAXROWS` yalnızca salt okunur sağlayıcılar için çalışır (diğer bir deyişle, burada `DBPROP_IRowsetChange` ve `DBPROP_IRowsetUpdate` olan **false**); Aksi takdirde bu özelliği desteklenmiyor.

- `DBPROP_MAXPENDINGROWS` göz ardı edilir; Sağlayıcı, kendi üst sınırını belirtir.

- `DBPROP_MAXOPENROWS` göz ardı edilir; Sağlayıcı, kendi üst sınırını belirtir.

- `DBPROP_CANHOLDROWS` göz ardı edilir; Sağlayıcı, kendi üst sınırını belirtir.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)