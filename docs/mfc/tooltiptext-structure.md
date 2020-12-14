---
description: ': TOOLTIPTEXT yapısı hakkında daha fazla bilgi edinin'
title: TOOLTIPTEXT Yapısı
ms.date: 11/04/2016
f1_keywords:
- TOOLTIPTEXT
helpviewer_keywords:
- TOOLTIPTEXT structure [MFC]
- tool tips [MFC], notifications
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
ms.openlocfilehash: 077d4c27392b626a0e9665851eadf227245029b6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264303"
---
# <a name="tooltiptext-structure"></a>TOOLTIPTEXT Yapısı

[Araç ipucu bildirim işleyicinizi](../mfc/handling-ttn-needtext-notification-for-tool-tips.md)yazarken **ToolTipText** yapısını kullanmanız gerekir. **ToolTipText** yapısının üyeleri şunlardır:

```cpp
typedef struct {
    NMHDR     hdr;        // required for all WM_NOTIFY messages
    LPTSTR    lpszText;   // see below
    TCHAR     szText[80]; // buffer for tool tip text
    HINSTANCE hinst;      // see below
    UINT      uflags;     // flag indicating how to interpret the
                          // idFrom member of the NMHDR structure
                          // that is included in the structure
} TOOLTIPTEXT, FAR *LPTOOLTIPTEXT;
```

*görüntüsünde*<br/>
Metin gerektiren aracı tanımlar. Bu yapının yalnızca ihtiyaç duyduğunuz tek üyesi, denetimin komut KIMLIĞIDIR. Denetimin komut KIMLIĞI, sözdizimiyle erişilen, **nmhdr** yapısının *ıdfrom* üyesi içinde olacaktır `hdr.idFrom` . **Nmhdr** yapısının üyelerinin tartışılması için bkz. [nmhdr](/windows/win32/api/richedit/ns-richedit-nmhdr) .

*lpszText*<br/>
Bir aracın metnini alacak dizenin adresi.

*szText*<br/>
Araç ipucu metnini alan arabellek. Bir uygulama, bir dize adresi belirtmeye alternatif olarak metni bu arabelleğe kopyalayabilir.

*hinst*<br/>
Araç ipucu metni olarak kullanılacak bir dize içeren örneğin tanıtıcısı. *LpszText* , araç ipucu metninin adresidir, bu üye null olur.

`TTN_NEEDTEXT`Bildirim iletisini işlerken, aşağıdaki yollarla görüntülenecek dizeyi belirtin:

- Metni *szText* üyesi tarafından belirtilen arabelleğe kopyalayın.

- Metni içeren arabelleğin adresini *lpszText* üyesine kopyalayın.

- Bir dize kaynağının tanımlayıcısını *lpszText* üyesine kopyalayın ve kaynağı içeren örneğin tanıtıcısını *hinst* üyesine kopyalayın.

## <a name="see-also"></a>Ayrıca bkz.

[CFrameWnd 'den türetilmemiş pencerelerin araç Ipuçları](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)
