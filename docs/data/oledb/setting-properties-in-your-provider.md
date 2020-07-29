---
title: Sağlayıcınızdaki Özellikleri Ayarlama
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB providers, properties
- properties [C++], OLE DB provider
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
ms.openlocfilehash: f5d5ac364096ea1a4505b2ead81f25367a9c9458
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212962"
---
# <a name="setting-properties-in-your-provider"></a>Sağlayıcınızdaki Özellikleri Ayarlama

İstediğiniz özelliğin özellik grubunu ve özellik KIMLIĞINI bulun. Daha fazla bilgi için, **OLE DB Programcı başvurusunda** [OLE DB Özellikler](/previous-versions/windows/desktop/ms722734(v=vs.85)) ' i inceleyin.

Sihirbaz tarafından oluşturulan sağlayıcı kodunda, özellik grubuna karşılık gelen özellik eşlemesini bulun. Özellik grubunun adı genellikle nesnenin adına karşılık gelir. Komut ve satır kümesi özellikleri komutta veya satır kümesinde bulunabilir; veri kaynağı ve başlatma özellikleri veri kaynağı nesnesinde bulunabilir.

Özellik eşlemesinde bir [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md) makrosu ekleyin. PROPERTY_INFO_ENTRY_EX dört parametre alır:

- Özelliğine karşılık gelen özellik KIMLIĞI. Özellik adının önüne ilk yedi karakteri ("DBPROP_") kaldırın. Örneğin, eklemek istiyorsanız `DBPROP_MAXROWS` `MAXROWS` ilk öğe olarak geçirin. Bu özel bir özelliktir, tam GUID adını geçirin (örneğin, `DBMYPROP_MYPROPERTY` ).

- Özelliğin değişken türü ( **OLE DB Programcı başvurusunda** [OLE DB Özellikler](/previous-versions/windows/desktop/ms722734(v=vs.85)) ). Veri türüne karşılık gelen VT_ türünü (VT_BOOL veya VT_I2) girin.

- Özelliğin okunabilir ve yazılabilir olduğunu ve ait olduğu grubu belirten bayraklar. Örneğin, aşağıdaki kod satır kümesi grubuna ait bir okuma/yazma özelliğini gösterir:

    ```cpp
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE
    ```

- Özelliğin taban değeri. Bu `VARIANT_FALSE` , örneğin, bir tamsayı türü için bir Boole türü veya sıfır olabilir. Özelliği, değiştirilmedikleri takdirde bu değere sahiptir.

    > [!NOTE]
    > Bazı özellikler, yer işaretleri veya güncelleştirme gibi diğer özelliklere bağlanır veya zincirleme yapılır. Bir tüketici bir özelliği true olarak ayarladığında, başka bir özellik de ayarlanabilir. OLE DB sağlayıcı şablonları, [CUtlProps:: OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)yöntemi aracılığıyla bunu destekler.

## <a name="properties-ignored-by-microsoft-ole-db-providers"></a>Microsoft OLE DB sağlayıcıları tarafından yoksayılan Özellikler

Microsoft OLE DB sağlayıcıları aşağıdaki OLE DB özelliklerini yoksayar:

- `DBPROP_MAXROWS`yalnızca salt okunurdur (yani ve olduğu) sağlayıcılar için geçerlidir `DBPROP_IRowsetChange` `DBPROP_IRowsetUpdate` **`false`** ; Aksi takdirde bu özellik desteklenmez.

- `DBPROP_MAXPENDINGROWS`yoksayıldı; sağlayıcı kendi sınırını belirtiyor.

- `DBPROP_MAXOPENROWS`yoksayıldı; sağlayıcı kendi sınırını belirtiyor.

- `DBPROP_CANHOLDROWS`yoksayıldı; sağlayıcı kendi sınırını belirtiyor.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonlarıyla çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)
