---
title: CREATESTRUCT Yapısı
ms.date: 11/04/2016
f1_keywords:
- CREATESTRUCT
helpviewer_keywords:
- CREATESTRUCT structure [MFC]
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
ms.openlocfilehash: 1de42ba3e26f7a06918a69358083e68f142836cc
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694705"
---
# <a name="createstruct-structure"></a>CREATESTRUCT Yapısı

`CREATESTRUCT` Yapısı, bir uygulamanın pencere yordamına geçirilen başlatma parametreleri tanımlar.

## <a name="syntax"></a>Sözdizimi

```
typedef struct tagCREATESTRUCT {
    LPVOID lpCreateParams;
    HANDLE hInstance;
    HMENU hMenu;
    HWND hwndParent;
    int cy;
    int cx;
    int y;
    int x;
    LONG style;
    LPCSTR lpszName;
    LPCSTR lpszClass;
    DWORD dwExStyle;
} CREATESTRUCT;
```

#### <a name="parameters"></a>Parametreler

*lpCreateParams*<br/>
Pencere oluşturmak için kullanılacak veri işaret eder.

*HINSTANCE*<br/>
Yeni pencere sahibi olan modülün modül örneğinin tutamacını tanımlar.

*hMenu*<br/>
Yeni pencere tarafından kullanılmak üzere menü tanımlar. Alt pencere, tamsayı kimliğini içerir.

*hwndParent*<br/>
Yeni pencere sahip penceresi tanımlar. Bu üye NULL ise yeni bir üst düzey penceresidir.

*CY*<br/>
Yeni pencere yüksekliğini belirtir.

*CX*<br/>
Yeni Pencere genişliğini belirtir.

*Y*<br/>
Yeni pencerenin sol üst köşesinin y koordinatını belirtir. Yeni pencere alt pencere ise üst pencere göreli koordinatları; Aksi halde ekran kaynağa göreli koordinatları.

*x*<br/>
Yeni pencerenin sol üst köşesinin x koordinatını belirtir. Yeni pencere alt pencere ise üst pencere göreli koordinatları; Aksi halde ekran kaynağa göreli koordinatları.

*Stil*<br/>
Yeni pencere belirtir [stil](../../mfc/reference/styles-used-by-mfc.md).

*lpszName*<br/>
Yeni Pencere adını belirten bir boş sonlandırılmış dizeye işaret eder.

*lpszClass*<br/>
İşaret yeni pencere Windows sınıf adı belirten null ile sonlandırılmış bir dize (bir [WNDCLASS](/windows/desktop/api/winuser/ns-winuser-tagwndclassa) yapısı; daha fazla bilgi için Windows SDK'sı bakın).

*dwExStyle*<br/>
Belirtir [Genişletilmiş](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) yeni pencere için.

## <a name="requirements"></a>Gereksinimler

**Başlık:** winuser.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)

