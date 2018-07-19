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
ms.openlocfilehash: 6036490b21ccbd86dfed56ea90226cbb2db8d596
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848476"
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
 *lpCreateParams*  
 Pencere oluşturmak için kullanılacak veri işaret eder.  
  
 *HINSTANCE*  
 Yeni pencere sahibi olan modülün modül örneğinin tutamacını tanımlar.  
  
 *hMenu*  
 Yeni pencere tarafından kullanılmak üzere menü tanımlar. Alt pencere, tamsayı kimliğini içerir.  
  
 *hwndParent*  
 Yeni pencere sahip penceresi tanımlar. Bu üye NULL ise yeni bir üst düzey penceresidir.  
  
 *CY*  
 Yeni pencere yüksekliğini belirtir.  
  
 *CX*  
 Yeni Pencere genişliğini belirtir.  
  
 *Y*  
 Yeni pencerenin sol üst köşesinin y koordinatını belirtir. Yeni pencere alt pencere ise üst pencere göreli koordinatları; Aksi halde ekran kaynağa göreli koordinatları.  
  
 *x*  
 Yeni pencerenin sol üst köşesinin x koordinatını belirtir. Yeni pencere alt pencere ise üst pencere göreli koordinatları; Aksi halde ekran kaynağa göreli koordinatları.  
  
 *Stil*  
 Yeni pencere belirtir [stil](../../mfc/reference/styles-used-by-mfc.md).  
  
 *lpszName*  
 Yeni Pencere adını belirten bir boş sonlandırılmış dizeye işaret eder.  
  
 *lpszClass*  
 İşaret yeni pencere Windows sınıf adı belirten null ile sonlandırılmış bir dize (bir [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) yapısı; daha fazla bilgi için Windows SDK'sı bakın).  
  
 *dwExStyle*  
 Belirtir [Genişletilmiş](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) yeni pencere için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** winuser.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri çağırmaları ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)


