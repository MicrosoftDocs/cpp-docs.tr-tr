---
title: CREATESTRUCT yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CREATESTRUCT
dev_langs:
- C++
helpviewer_keywords:
- CREATESTRUCT structure [MFC]
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e51aed1eb7f74c721a5a4da092f205a2492ba5f7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="createstruct-structure"></a>CREATESTRUCT Yapısı
`CREATESTRUCT` Yapısı uygulama penceresi yordamına geçirilen başlatma parametreleri tanımlar.  
  
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
 `lpCreateParams`  
 Pencere oluşturmak için kullanılacak veri noktalarına.  
  
 `hInstance`  
 Yeni pencerede sahibi modülü Modül örneğinin işleyicisini tanımlar.  
  
 `hMenu`  
 Yeni pencere tarafından kullanılmak üzere menü tanımlar. Alt pencere, tamsayı kimliğini içerir  
  
 `hwndParent`  
 Yeni pencerede sahibi penceresi tanımlar. Bu üye **NULL** yeni pencere üst düzey bir pencere ise.  
  
 `cy`  
 Yeni pencerede yüksekliğini belirtir.  
  
 `cx`  
 Yeni Pencere genişliğini belirtir.  
  
 `y`  
 Yeni pencerenin sol üst köşesinin y koordinatını belirtir. Yeni pencere alt pencere ise koordinatlar üst pencere göre belirlenir; Aksi takdirde koordinatlar ekran kaynağa göre belirlenir.  
  
 `x`  
 Yeni pencerenin sol üst köşesinin x koordinatını belirtir. Yeni pencere alt pencere ise koordinatlar üst pencere göre belirlenir; Aksi takdirde koordinatlar ekran kaynağa göre belirlenir.  
  
 `style`  
 Yeni pencere belirtir [stili](../../mfc/reference/styles-used-by-mfc.md).  
  
 `lpszName`  
 Noktaları null ile sonlandırılmış dizeye yeni pencerenin adını belirtir.  
  
 `lpszClass`  
 İşaret yeni pencerenin Windows sınıf adını belirten null ile sonlandırılmış bir dize (bir [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) yapısı; daha fazla bilgi için Windows SDK'sı bakın).  
  
 `dwExStyle`  
 Belirtir [genişletilmiş stili](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) yeni pencere için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)


