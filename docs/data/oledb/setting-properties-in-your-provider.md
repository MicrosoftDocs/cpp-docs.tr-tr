---
description: 'Hakkında daha fazla bilgi edinin: sağlayıcınızdaki özellikleri ayarlama'
title: Sağlayıcınızdaki Özellikleri Ayarlama
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB providers, properties
- properties [C++], OLE DB provider
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
ms.openlocfilehash: e85fddfb741fe89869d18531bb172201eaa14753
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316693"
---
# <a name="setting-properties-in-your-provider"></a>Sağlayıcınızdaki Özellikleri Ayarlama

İstediğiniz özelliğin özellik grubunu ve özellik KIMLIĞINI bulun. Daha fazla bilgi için, **OLE DB Programcı başvurusunda** [OLE DB Özellikler](/previous-versions/windows/desktop/ms722734(v=vs.85)) ' i inceleyin.

Sihirbaz tarafından oluşturulan sağlayıcı kodunda, özellik grubuna karşılık gelen özellik eşlemesini bulun. Özellik grubunun adı genellikle nesnenin adına karşılık gelir. Komut ve satır kümesi özellikleri komutta veya satır kümesinde bulunabilir; veri kaynağı ve başlatma özellikleri veri kaynağı nesnesinde bulunabilir.

Özellik eşlemesinde bir [PROPERTY_INFO_ENTRY_EX](./macros-for-ole-db-provider-templates.md#property_info_entry_ex) makrosu ekleyin. PROPERTY_INFO_ENTRY_EX dört parametre alır:

- Özelliğine karşılık gelen özellik KIMLIĞI. Özellik adının önüne ilk yedi karakteri ("DBPROP_") kaldırın. Örneğin, eklemek istiyorsanız `DBPROP_MAXROWS` `MAXROWS` ilk öğe olarak geçirin. Bu özel bir özelliktir, tam GUID adını geçirin (örneğin, `DBMYPROP_MYPROPERTY` ).

- Özelliğin değişken türü ( **OLE DB Programcı başvurusunda** [OLE DB Özellikler](/previous-versions/windows/desktop/ms722734(v=vs.85)) ). Veri türüne karşılık gelen VT_ türünü (VT_BOOL veya VT_I2) girin.

- Özelliğin okunabilir ve yazılabilir olduğunu ve ait olduğu grubu belirten bayraklar. Örneğin, aşağıdaki kod satır kümesi grubuna ait bir okuma/yazma özelliğini gösterir:

    ```cpp
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE
    ```

- Özelliğin taban değeri. Bu `VARIANT_FALSE` , örneğin, bir tamsayı türü için bir Boole türü veya sıfır olabilir. Özelliği, değiştirilmedikleri takdirde bu değere sahiptir.

    > [!NOTE]
    > Bazı özellikler, yer işaretleri veya güncelleştirme gibi diğer özelliklere bağlanır veya zincirleme yapılır. Bir tüketici bir özelliği true olarak ayarladığında, başka bir özellik de ayarlanabilir. OLE DB sağlayıcı şablonları, [CUtlProps:: OnPropertyChanged](./cutlprops-class.md#onpropertychanged)yöntemi aracılığıyla bunu destekler.

## <a name="properties-ignored-by-microsoft-ole-db-providers"></a>Microsoft OLE DB sağlayıcıları tarafından yoksayılan Özellikler

Microsoft OLE DB sağlayıcıları aşağıdaki OLE DB özelliklerini yoksayar:

- `DBPROP_MAXROWS` yalnızca salt okunurdur (yani ve olduğu) sağlayıcılar için geçerlidir `DBPROP_IRowsetChange` `DBPROP_IRowsetUpdate` **`false`** ; Aksi takdirde bu özellik desteklenmez.

- `DBPROP_MAXPENDINGROWS` yoksayıldı; sağlayıcı kendi sınırını belirtiyor.

- `DBPROP_MAXOPENROWS` yoksayıldı; sağlayıcı kendi sınırını belirtiyor.

- `DBPROP_CANHOLDROWS` yoksayıldı; sağlayıcı kendi sınırını belirtiyor.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonlarıyla çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)
