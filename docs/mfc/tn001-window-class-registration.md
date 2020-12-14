---
description: 'Şu konuda daha fazla bilgi edinin: TN001: pencere sınıfı kaydı'
title: 'TN001: Pencere Sınıfı Kaydı'
ms.date: 11/04/2016
f1_keywords:
- vc.registration
helpviewer_keywords:
- TN001
- WNDCLASS [MFC]
- AfxRegisterClass function
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
ms.openlocfilehash: fc54b6f783a50bb35f87f542772b9a1921f1f7b7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216112"
---
# <a name="tn001-window-class-registration"></a>TN001: Pencere Sınıfı Kaydı

Bu notta, Microsoft Windows tarafından gerek duyulan özel [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw)es 'YI kaydeden MFC yordamları açıklanmaktadır. `WNDCLASS`MFC ve Windows tarafından kullanılan belirli öznitelikler ele alınmıştır.

## <a name="the-problem"></a>Sorun

Bir [CWnd](../mfc/reference/cwnd-class.md) nesnesinin, `HWND` Windows 'daki bir tanıtıcı gibi öznitelikleri iki yerde depolanır: pencere nesnesi ve `WNDCLASS` . Adı, `WNDCLASS` *LpszClassName* parametresinde [CWnd:: Create](../mfc/reference/cwnd-class.md#create) ve [CFrameWnd:: Create](../mfc/reference/cframewnd-class.md#create) gibi genel pencere oluşturma işlevlerine geçirilir.

Bu `WNDCLASS` , dört bir nedenle kaydedilmelidir:

- Belirtilen MFC kullanarak örtülü olarak `WNDCLASS` .

- Altsınıflama bir Windows denetimi (veya başka bir denetim) örtük olarak.

- Açıkça MFC [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) veya [AfxRegisterClass](../mfc/reference/application-information-and-management.md#afxregisterclass)çağırarak.

- Windows Routine [RegisterClass](/windows/win32/api/winuser/nf-winuser-registerclassw)çağırarak açıkça.

## <a name="wndclass-fields"></a>WNDCLASS alanları

`WNDCLASS`Yapı, bir pencere sınıfını tanımlayan çeşitli alanlardan oluşur. Aşağıdaki tabloda, alanlar gösterilmektedir ve bunların bir MFC uygulamasında nasıl kullanıldığı belirtilir:

|Alan|Açıklama|
|-----------|-----------------|
|*lpfnWndProc*|pencere proc bir olmalıdır `AfxWndProc`|
|*cbClsExtra*|kullanılmıyor (sıfır olmalıdır)|
|*cbWndExtra*|kullanılmıyor (sıfır olmalıdır)|
|*HINSTANCE*|[AfxGetInstanceHandle](../mfc/reference/application-information-and-management.md#afxgetinstancehandle) ile otomatik olarak doldurulmuştur|
|*HICON*|çerçeve pencereleri simgesi, aşağıya bakın|
|*hCursor*|fare üzerine geldiğinde imleci, aşağıya bakın|
|*hbrBackground*|arka plan rengi, aşağıya bakın|
|*lpszMenuName*|kullanılmıyor (NULL olmalıdır)|
|*lpszClassName*|sınıf adı, aşağıya bakın|

## <a name="provided-wndclasses"></a>Sunulan WNDCLASSes

Daha önceden tanımlanmış birkaç pencere sınıfı sağlanmış olan MFC 'nin önceki sürümleri (MFC 4,0 ' den önce). Bu pencere sınıfları artık varsayılan olarak sağlanmaz. Uygulamalar `AfxRegisterWndClass` uygun parametrelerle kullanılmalıdır.

Uygulama, belirtilen kaynak KIMLIĞINE sahip bir kaynak sağlıyorsa (örneğin, AFX_IDI_STD_FRAME), MFC bu kaynağı kullanacaktır. Aksi takdirde, varsayılan kaynağı kullanır. Simge için, standart uygulama simgesi kullanılır ve imleç için standart ok imleci kullanılır.

İki simge, tek belge türlerine sahip MDI uygulamalarını destekler: Ana uygulama için bir simge, IIC Document/MDIChild Windows için diğer simge. Farklı simgelerle birden çok belge türü için ek `WNDCLASS` es kaydetmelisiniz veya [CFrameWnd:: LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) işlevini kullanmanız gerekir.

`CFrameWnd::LoadFrame``WNDCLASS`, ilk parametre olarak belirttiğiniz SIMGE kimliğini ve aşağıdaki standart öznitelikleri kullanarak bir kaydeder:

- sınıf stili: CS_DBLCLKS &#124; CS_HREDRAW &#124; CS_VREDRAW;

- simge AFX_IDI_STD_FRAME

- ok imleci

- COLOR_WINDOW arka plan rengi

Öğesinin istemci alanı MDICLIENT penceresi tarafından tamamen kapsamında olduğundan, [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) için arka plan rengi ve imleç değerleri kullanılmaz `CMDIFrameWnd` .  Microsoft, altsınıflama **MDICLIENT** penceresini teşvik etmez, mümkünse standart renkleri ve imleç türlerini kullanın.

## <a name="subclassing-and-superclassing-controls"></a>Altsınıflama ve superclassing denetimleri

Bir Windows denetimini (örneğin, [CButton](../mfc/reference/cbutton-class.md)) alt sınıfı veya üst sınıfı yaparsanız, sınıfınız `WNDCLASS` Bu denetimin Windows uygulamasında belirtilen öznitelikleri otomatik olarak alır.

## <a name="the-afxregisterwndclass-function"></a>AfxRegisterWndClass Işlevi

MFC, bir pencere sınıfını kaydetmek için yardımcı işlev sağlar. Bir öznitelikler kümesi (pencere sınıfı stili, imleç, arka plan fırçası ve simge) verildiğinde, yapay bir ad oluşturulur ve ortaya çıkan pencere sınıfı kaydedilir. Örneğin,

```
const char* AfxRegisterWndClass(UINT nClassStyle,
    HCURSOR hCursor,
    HBRUSH hbrBackground,
    HICON hIcon);
```

Bu işlev, oluşturulan kayıtlı pencere sınıfı adının geçici bir dizesini döndürür. Bu işlev hakkında daha fazla bilgi için bkz. [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass).

Döndürülen dize, statik dize arabelleğinin geçici bir işaretçisidir. Bir sonraki çağrıya kadar geçerli olur `AfxRegisterWndClass` . Bu dizeyi etrafında tutmak istiyorsanız, bu örnekte olduğu gibi bir [CString](../atl-mfc-shared/using-cstring.md) değişkeninde saklayın:

```
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);

...
CWnd* pWnd = new CWnd;
pWnd->Create(strWndClass, ...);

...
```

`AfxRegisterWndClass` pencere sınıfı kayıt (hatalı parametre veya Windows belleği dışında) başarısız olursa bir [CResourceException](../mfc/reference/cresourceexception-class.md) oluşturur.

## <a name="the-registerclass-and-afxregisterclass-functions"></a>RegisterClass ve AfxRegisterClass Işlevleri

Sağladığından daha karmaşık bir şey yapmak istiyorsanız `AfxRegisterWndClass` , WINDOWS API 'sini `RegisterClass` veya MFC işlevini çağırabilirsiniz `AfxRegisterClass` . `CWnd`, [CFrameWnd](../mfc/reference/cframewnd-class.md) ve [Cmdictepdwnd](../mfc/reference/cmdichildwnd-class.md) `Create` işlevleri, ilk parametre olarak Window sınıfı için bir *lpszClassName* dize adı alır. Kayıtlı pencere sınıfı adını, kaydetmek için kullandığınız yöntemden bağımsız olarak kullanabilirsiniz.

`AfxRegisterClass` `AfxRegisterWndClass` Win32 ÜZERINDE bir dll içinde (veya) kullanılması önemlidir. Win32, DLL tarafından kaydedilen sınıfların kaydını otomatik olarak kaldırmaz, bu nedenle DLL sonlandırıldığında sınıfların kaydını açıkça silmeniz gerekir. `AfxRegisterClass`Bunun yerine kullanarak `RegisterClass` , sizin için otomatik olarak işlenir. `AfxRegisterClass` DLL 'niz tarafından kaydedilen benzersiz sınıfların bir listesini tutar ve DLL sonlandırıldığında otomatik olarak bunların kaydını siler. `RegisterClass`DLL 'de kullandığınızda, dll sonlandırıldığı zaman tüm sınıfların kaydının kaydedildiğinden emin olmanız gerekir ( [DllMain](/windows/win32/Dlls/dllmain) işlevinizde). Bunun yapılmaması, `RegisterClass` başka bir istemci UYGULAMASı dll 'nizi kullanmayı denediğinde beklenmedik şekilde başarısız olmasına neden olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
