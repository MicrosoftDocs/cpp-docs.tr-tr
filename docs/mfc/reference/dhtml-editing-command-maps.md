---
title: DHTML Düzenleme Komutu Eşlemeleri
ms.date: 11/04/2016
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
ms.openlocfilehash: f4bbfb500e8de9594bbaa334b4e227caeaa845da
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837417"
---
# <a name="dhtml-editing-command-maps"></a>DHTML Düzenleme Komutu Eşlemeleri

Aşağıdaki makrolar, [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)ile TÜRETILMIŞ sınıflarda DHTML Düzenle komutlarını eşlemek için kullanılabilir. Kullanımları hakkında bir örnek için bkz. [HtmlEdit Sample](../../overview/visual-cpp-samples.md).

### <a name="dhtml-editing-command-map-macros"></a>DHTML düzenlemesi komut eşleme makroları

|Ad|Açıklama|
|-|-|
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|Bir sınıfta DHTML düzenlemesi komut eşlemesi bildirir.|
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|Bir sınıf içindeki DHTML düzenlemesi komut haritasının tanımını başlatır.|
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|DHTML düzenlemesi komut haritasının sonunu işaretler.|
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|Bir komut KIMLIĞINI HTML düzenlemesi komutuyla eşler.|
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|Bir komut KIMLIĞINI HTML düzenlemesi komutuyla ve ileti işleyicisine eşler.|
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|Bir komut KIMLIĞINI HTML Editing komutuyla ve Kullanıcı arabirimi öğesiyle eşleştirir.|
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|Bir komut KIMLIĞINI HTML Editing komutuyla, ileti işleyicisine ve Kullanıcı arabirimi öğesiyle eşleştirir.|

## <a name="declare_dhtmlediting_cmdmap"></a><a name="declare_dhtmlediting_cmdmap"></a> DECLARE_DHTMLEDITING_CMDMAP

Bir sınıfta DHTML düzenlemesi komut eşlemesi bildirir.

```
DECLARE_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Sınıfın adı.

### <a name="remarks"></a>Açıklamalar

Bu makro, [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)tarafından türetilen sınıfların tanımında kullanılacaktır.

Eşlemeyi uygulamak için [BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap) kullanın.

### <a name="example"></a>Örnek

Bkz. [HtmlEdit örneği](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxhtml. h

## <a name="begin_dhtmlediting_cmdmap"></a><a name="begin_dhtmlediting_cmdmap"></a> BEGIN_DHTMLEDITING_CMDMAP

Bir sınıf içindeki DHTML düzenlemesi komut haritasının tanımını başlatır.

```
BEGIN_DHTMLEDITING_CMDMAP(className)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
DHTML Düzen komutu eşlemesini içeren sınıfın adı. Bu sınıf doğrudan veya dolaylı olarak [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) 'dan türetilmelidir ve [DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap) makrosunu sınıf tanımına dahil etmelidir.

### <a name="remarks"></a>Açıklamalar

Kullanıcı arabirimi komutlarını HTML düzenlemesi komutlarına eşlemek için sınıfınıza bir DHTML Düzenle komut eşlemesi ekleyin.

BEGIN_DHTMLEDITING_CMDMAP makrosunu sınıfın uygulama (. cpp) dosyasına ve ardından sınıfın eşlenecek komutlara yönelik [DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry) makroları (örneğin, ID_EDIT_CUT 'den IDM_CUT 'e) yerleştirin. Olay eşlemesinin sonunu işaretlemek için [END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap) makrosunu kullanın.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxhtml. h

## <a name="end_dhtmlediting_cmdmap"></a><a name="end_dhtmlediting_cmdmap"></a> END_DHTMLEDITING_CMDMAP

DHTML düzenlemesi komut haritasının sonunu işaretler.

```
END_DHTMLEDITING_CMDMAP()
```

### <a name="remarks"></a>Açıklamalar

[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)ile birlikte kullanın.

### <a name="example"></a>Örnek

Bkz. [HtmlEdit örneği](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxhtml. h

## <a name="dhtmlediting_cmd_entry"></a><a name="dhtmlediting_cmd_entry"></a> DHTMLEDITING_CMD_ENTRY

Bir komut KIMLIĞINI HTML düzenlemesi komutuyla eşler.

```
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut KIMLIĞI (örneğin ID_EDIT_COPY).

*Dhtmlcmdıd*<br/>
*CmdID* 'nın eşlendiği HTML Editing komutu (örneğin, IDM_COPY).

### <a name="example"></a>Örnek

Bkz. [HtmlEdit örneği](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxhtml. h

## <a name="dhtmlediting_cmd_entry_func"></a><a name="dhtmlediting_cmd_entry_func"></a> DHTMLEDITING_CMD_ENTRY_FUNC

Bir komut KIMLIĞINI HTML düzenlemesi komutuyla ve ileti işleyicisine eşler.

```
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut KIMLIĞI (örneğin ID_EDIT_COPY).

*Dhtmlcmdıd*<br/>
*CmdID* 'nın eşlendiği HTML Editing komutu (örneğin, IDM_COPY).

*member_func_name*<br/>
Komutun eşlendiği ileti işleyicisi işlevinin adı.

### <a name="example"></a>Örnek

Bkz. [HtmlEdit örneği](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxhtml. h

## <a name="dhtmlediting_cmd_entry_type"></a><a name="dhtmlediting_cmd_entry_type"></a> DHTMLEDITING_CMD_ENTRY_TYPE

Bir komut KIMLIĞINI HTML Editing komutuyla ve Kullanıcı arabirimi öğesiyle eşleştirir.

```
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut KIMLIĞI (örneğin ID_EDIT_COPY).

*Dhtmlcmdıd*<br/>
*CmdID* 'nın eşlendiği HTML Editing komutu (örneğin, IDM_COPY).

*elemType*<br/>
Kullanıcı arabirimi öğe türü; AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX veya AFX_UI_ELEMTYPE_RADIO biridir.

### <a name="example"></a>Örnek

Bkz. [HtmlEdit örneği](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxhtml. h

## <a name="dhtmlediting_cmd_entry_func_type"></a><a name="dhtmlediting_cmd_entry_func_type"></a> DHTMLEDITING_CMD_ENTRY_FUNC_TYPE

Bir komut KIMLIĞINI HTML Editing komutuyla, ileti işleyicisine ve Kullanıcı arabirimi öğesiyle eşleştirir.

```
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut KIMLIĞI (örneğin ID_EDIT_COPY).

*Dhtmlcmdıd*<br/>
*CmdID* 'nın eşlendiği HTML Editing komutu (örneğin, IDM_COPY).

*member_func_name*<br/>
Komutun eşlendiği ileti işleyicisi işlevinin adı.

*elemType*<br/>
Kullanıcı arabirimi öğe türü; AFX_UI_ELEMTYPE_NORMAL, AFX_UI_ELEMTYPE_CHECKBOX veya AFX_UI_ELEMTYPE_RADIO biridir.

### <a name="example"></a>Örnek

Bkz. [HtmlEdit örneği](../../overview/visual-cpp-samples.md).

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxhtml. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
