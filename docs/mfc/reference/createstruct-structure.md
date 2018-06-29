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
ms.openlocfilehash: b7bc510f0d0cfc88476c9e222f51bcfeb958e31a
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078473"
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
 *lpCreateParams*  
 Pencere oluşturmak için kullanılacak veri noktalarına.  
  
 *HINSTANCE*  
 Yeni pencerede sahibi modülü Modül örneğinin işleyicisini tanımlar.  
  
 *hMenu*  
 Yeni pencere tarafından kullanılmak üzere menü tanımlar. Alt pencere, tamsayı kimliğini içerir  
  
 *hwndParent*  
 Yeni pencerede sahibi penceresi tanımlar. Bu üye **NULL** yeni pencere üst düzey bir pencere ise.  
  
 *CY*  
 Yeni pencerede yüksekliğini belirtir.  
  
 *CX*  
 Yeni Pencere genişliğini belirtir.  
  
 *Y*  
 Yeni pencerenin sol üst köşesinin y koordinatını belirtir. Yeni pencere alt pencere ise koordinatlar üst pencere göre belirlenir; Aksi takdirde koordinatlar ekran kaynağa göre belirlenir.  
  
 *x*  
 Yeni pencerenin sol üst köşesinin x koordinatını belirtir. Yeni pencere alt pencere ise koordinatlar üst pencere göre belirlenir; Aksi takdirde koordinatlar ekran kaynağa göre belirlenir.  
  
 *Stili*  
 Yeni pencere belirtir [stili](../../mfc/reference/styles-used-by-mfc.md).  
  
 *lpszName*  
 Noktaları null ile sonlandırılmış dizeye yeni pencerenin adını belirtir.  
  
 *lpszClass*  
 İşaret yeni pencerenin Windows sınıf adını belirten null ile sonlandırılmış bir dize (bir [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) yapısı; daha fazla bilgi için Windows SDK'sı bakın).  
  
 *dwExStyle*  
 Belirtir [genişletilmiş stili](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) yeni pencere için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)


