---
title: Sağlayıcınızdaki Özellikleri Ayarlama
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB providers, properties
- properties [C++], OLE DB provider
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
ms.openlocfilehash: 905a9bb32544dbd7453d46362e100047516d22a8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209579"
---
# <a name="setting-properties-in-your-provider"></a>Sağlayıcınızdaki Özellikleri Ayarlama

İstediğiniz özelliğin özellik grubunu ve özellik KIMLIĞINI bulun. Daha fazla bilgi için, **OLE DB Programcı başvurusunda** [OLE DB Özellikler](/previous-versions/windows/desktop/ms722734(v=vs.85)) ' i inceleyin.

Sihirbaz tarafından oluşturulan sağlayıcı kodunda, özellik grubuna karşılık gelen özellik eşlemesini bulun. Özellik grubunun adı genellikle nesnenin adına karşılık gelir. Komut ve satır kümesi özellikleri komutta veya satır kümesinde bulunabilir; veri kaynağı ve başlatma özellikleri veri kaynağı nesnesinde bulunabilir.

Özellik eşlemesinde bir [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md) makrosu ekleyin. PROPERTY_INFO_ENTRY_EX dört parametre alır:

- Özelliğine karşılık gelen özellik KIMLIĞI. Özellik adının önüne ilk yedi karakteri ("DBPROP_") kaldırın. Örneğin, `DBPROP_MAXROWS`eklemek istiyorsanız, `MAXROWS` ilk öğe olarak geçirin. Bu özel bir özelliktir, tam GUID adını geçirin (örneğin, `DBMYPROP_MYPROPERTY`).

- Özelliğin değişken türü ( **OLE DB Programcı başvurusunda** [OLE DB Özellikler](/previous-versions/windows/desktop/ms722734(v=vs.85)) ). Veri türüne karşılık gelen VT_ türünü (VT_BOOL veya VT_I2) girin.

- Özelliğin okunabilir ve yazılabilir olduğunu ve ait olduğu grubu belirten bayraklar. Örneğin, aşağıdaki kod satır kümesi grubuna ait bir okuma/yazma özelliğini gösterir:

    ```cpp
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE
    ```

- Özelliğin taban değeri. Bu, örneğin bir Boole türü için `VARIANT_FALSE` veya bir tamsayı türü için sıfır olabilir. Özelliği, değiştirilmedikleri takdirde bu değere sahiptir.

    > [!NOTE]
    > Bazı özellikler, yer işaretleri veya güncelleştirme gibi diğer özelliklere bağlanır veya zincirleme yapılır. Bir tüketici bir özelliği true olarak ayarladığında, başka bir özellik de ayarlanabilir. OLE DB sağlayıcı şablonları, [CUtlProps:: OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)yöntemi aracılığıyla bunu destekler.

## <a name="properties-ignored-by-microsoft-ole-db-providers"></a>Microsoft OLE DB sağlayıcıları tarafından yoksayılan Özellikler

Microsoft OLE DB sağlayıcıları aşağıdaki OLE DB özelliklerini yoksayar:

- `DBPROP_MAXROWS` yalnızca salt okuma sağlayıcılar için geçerlidir (yani, `DBPROP_IRowsetChange` ve `DBPROP_IRowsetUpdate` **false**'dur); Aksi takdirde bu özellik desteklenmez.

- `DBPROP_MAXPENDINGROWS` yoksayıldı; sağlayıcı kendi sınırını belirtiyor.

- `DBPROP_MAXOPENROWS` yoksayıldı; sağlayıcı kendi sınırını belirtiyor.

- `DBPROP_CANHOLDROWS` yoksayıldı; sağlayıcı kendi sınırını belirtiyor.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)
