---
title: DHTML Düzenleme Komutu Eşlemeleri
ms.date: 11/04/2016
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
ms.openlocfilehash: 62b388eb178be018655ea2b2be00d7321da50335
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365816"
---
# <a name="dhtml-editing-command-maps"></a>DHTML Düzenleme Komutu Eşlemeleri

Aşağıdaki makrolar [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)türetilmiş sınıflarda DHTML düzenleme komutları eşlemek için kullanılabilir. Kullanımörnekleri için [HTMLEdit Örneği'ne](../../overview/visual-cpp-samples.md)bakın.

### <a name="dhtml-editing-command-map-macros"></a>DHTML Düzenleme Komut Haritası Makroları

|||
|-|-|
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|Bir sınıfta bir DHTML düzenleme komut haritası bildirir.|
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|Bir sınıf içinde bir DHTML düzenleme komut eşlemi tanımını başlatır.|
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|DHTML düzenleme komut haritasının sonunu işaretler.|
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|Komut kimliğini HTML düzenleme komutuyla eşler.|
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|Komut kimliğini HTML düzenleme komutu ve ileti işleyicisi ile eşler.|
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|Komut kimliğini HTML düzenleme komutu ve kullanıcı arabirimi öğesiyle eşler.|
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|Komut kimliğini HTML düzenleme komutu, ileti işleyicisi ve kullanıcı arabirimi öğesiyle eşler.|

## <a name="declare_dhtmlediting_cmdmap"></a><a name="declare_dhtmlediting_cmdmap"></a>DECLARE_DHTMLEDITING_CMDMAP

Bir sınıfta bir DHTML düzenleme komut haritası bildirir.

```
DECLARE_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>Parametreler

*Classname*<br/>
Sınıfın adı.

### <a name="remarks"></a>Açıklamalar

Bu makro [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)türetilmiş sınıfların tanımında kullanılacaktır.

Haritayı uygulamak için [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap) kullanın.

### <a name="example"></a>Örnek

Bkz. [HTMLEdit Örneği](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxhtml.h

## <a name="begin_dhtmlediting_cmdmap"></a><a name="begin_dhtmlediting_cmdmap"></a>BEGIN_DHTMLEDITING_CMDMAP

Bir sınıf içinde bir DHTML düzenleme komut eşlemi tanımını başlatır.

```
BEGIN_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>Parametreler

*Classname*<br/>
DHTML düzenleme komut eşlemini içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak [CHtmlEditView'den](../../mfc/reference/chtmleditview-class.md) türemelidir ve [DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap) makroyu sınıf tanımına dahil etmelidir.

### <a name="remarks"></a>Açıklamalar

Kullanıcı arabirimi komutlarını HTML düzenleme komutlarına eşlemek için sınıfınıza bir DHTML düzenleme komut haritası ekleyin.

BEGIN_DHTMLEDITING_CMDMAP makroyu sınıfın uygulama (.cpp) dosyasına yerleştirin ve ardından sınıfın eşlenebilmek için [DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry) makroları (örneğin, ID_EDIT_CUT'den IDM_CUT' ye) yerleştirin. Olay haritasının sonunu işaretlemek için [END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap) makroyu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxhtml.h

## <a name="end_dhtmlediting_cmdmap"></a><a name="end_dhtmlediting_cmdmap"></a>END_DHTMLEDITING_CMDMAP

DHTML düzenleme komut haritasının sonunu işaretler.

```
END_DHTMLEDITING_CMDMAP()
```

### <a name="remarks"></a>Açıklamalar

[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)ile birlikte kullanın.

### <a name="example"></a>Örnek

Bkz. [HTMLEdit Örneği](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxhtml.h

## <a name="dhtmlediting_cmd_entry"></a><a name="dhtmlediting_cmd_entry"></a>DHTMLEDITING_CMD_ENTRY

Komut kimliğini HTML düzenleme komutuyla eşler.

```
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği (ID_EDIT_COPY gibi).

*dhtmlcmdID*<br/>
*CMDID* haritalarının (IDM_COPY gibi) HTML düzenleme komutu.

### <a name="example"></a>Örnek

Bkz. [HTMLEdit Örneği](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxhtml.h

## <a name="dhtmlediting_cmd_entry_func"></a><a name="dhtmlediting_cmd_entry_func"></a>DHTMLEDITING_CMD_ENTRY_FUNC

Komut kimliğini HTML düzenleme komutu ve ileti işleyicisi ile eşler.

```
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği (ID_EDIT_COPY gibi).

*dhtmlcmdID*<br/>
*CMDID* haritalarının (IDM_COPY gibi) HTML düzenleme komutu.

*member_func_name*<br/>
Komutun eşlendiği ileti işleyicisi işlevinin adı.

### <a name="example"></a>Örnek

Bkz. [HTMLEdit Örneği](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxhtml.h

## <a name="dhtmlediting_cmd_entry_type"></a><a name="dhtmlediting_cmd_entry_type"></a>DHTMLEDITING_CMD_ENTRY_TYPE

Komut kimliğini HTML düzenleme komutu ve kullanıcı arabirimi öğesiyle eşler.

```
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği (ID_EDIT_COPY gibi).

*dhtmlcmdID*<br/>
*CMDID* haritalarının (IDM_COPY gibi) HTML düzenleme komutu.

*elemType*<br/>
Kullanıcı arabirimi öğesi türü; AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX veya AFX_UI_ELEMTYPE_RADIO biri.

### <a name="example"></a>Örnek

Bkz. [HTMLEdit Örneği](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxhtml.h

## <a name="dhtmlediting_cmd_entry_func_type"></a><a name="dhtmlediting_cmd_entry_func_type"></a>DHTMLEDITING_CMD_ENTRY_FUNC_TYPE

Komut kimliğini HTML düzenleme komutu, ileti işleyicisi ve kullanıcı arabirimi öğesiyle eşler.

```
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği (ID_EDIT_COPY gibi).

*dhtmlcmdID*<br/>
*CMDID* haritalarının (IDM_COPY gibi) HTML düzenleme komutu.

*member_func_name*<br/>
Komutun eşlendiği ileti işleyicisi işlevinin adı.

*elemType*<br/>
Kullanıcı arabirimi öğesi türü; AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX veya AFX_UI_ELEMTYPE_RADIO biri.

### <a name="example"></a>Örnek

Bkz. [HTMLEdit Örneği](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxhtml.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
