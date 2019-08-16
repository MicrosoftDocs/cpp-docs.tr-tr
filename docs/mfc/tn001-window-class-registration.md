---
title: 'TN001: Pencere sınıfı kaydı'
ms.date: 11/04/2016
f1_keywords:
- vc.registration
helpviewer_keywords:
- TN001
- WNDCLASS [MFC]
- AfxRegisterClass function
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
ms.openlocfilehash: 95e35ddd6f55c955bc2adb7b4db2460ae84a6dc7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513553"
---
# <a name="tn001-window-class-registration"></a>TN001: Pencere sınıfı kaydı

Bu notta, Microsoft Windows tarafından gerek duyulan özel [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw)es 'YI kaydeden MFC yordamları açıklanmaktadır. MFC `WNDCLASS` ve Windows tarafından kullanılan belirli öznitelikler ele alınmıştır.

## <a name="the-problem"></a>Sorun

Bir [CWnd](../mfc/reference/cwnd-class.md) nesnesinin, Windows 'daki bir `HWND` tanıtıcı gibi öznitelikleri iki yerde depolanır: `WNDCLASS`pencere nesnesi ve. Adı `WNDCLASS` , *lpszClassName* parametresinde [CWnd:: Create](../mfc/reference/cwnd-class.md#create) ve [CFrameWnd:: Create](../mfc/reference/cframewnd-class.md#create) gibi genel pencere oluşturma işlevlerine geçirilir.

Bu `WNDCLASS` , dört bir nedenle kaydedilmelidir:

- Belirtilen `WNDCLASS`MFC kullanarak örtülü olarak.

- Altsınıflama bir Windows denetimi (veya başka bir denetim) örtük olarak.

- Açıkça MFC [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) veya [AfxRegisterClass](../mfc/reference/application-information-and-management.md#afxregisterclass)çağırarak.

- Windows Routine [RegisterClass](/windows/win32/api/winuser/nf-winuser-registerclassw)çağırarak açıkça.

## <a name="wndclass-fields"></a>WNDCLASS alanları

Yapı `WNDCLASS` , bir pencere sınıfını tanımlayan çeşitli alanlardan oluşur. Aşağıdaki tabloda, alanlar gösterilmektedir ve bunların bir MFC uygulamasında nasıl kullanıldığı belirtilir:

|Alan|Açıklama|
|-----------|-----------------|
|*lpfnWndProc*|pencere proc bir olmalıdır`AfxWndProc`|
|*cbClsExtra*|kullanılmıyor (sıfır olmalıdır)|
|*cbWndExtra*|kullanılmıyor (sıfır olmalıdır)|
|*HINSTANCE*|[AfxGetInstanceHandle](../mfc/reference/application-information-and-management.md#afxgetinstancehandle) ile otomatik olarak doldurulmuştur|
|*HICON*|çerçeve pencereleri simgesi, aşağıya bakın|
|*hCursor*|fare üzerine geldiğinde imleci, aşağıya bakın|
|*hbrBackground*|arka plan rengi, aşağıya bakın|
|*lpszMenuName*|kullanılmıyor (NULL olmalıdır)|
|*lpszClassName*|sınıf adı, aşağıya bakın|

## <a name="provided-wndclasses"></a>Sunulan WNDCLASSes

Daha önceden tanımlanmış birkaç pencere sınıfı sağlanmış olan MFC 'nin önceki sürümleri (MFC 4,0 ' den önce). Bu pencere sınıfları artık varsayılan olarak sağlanmaz. `AfxRegisterWndClass` Uygulamalar uygun parametrelerle kullanılmalıdır.

Uygulama, belirtilen kaynak KIMLIĞINE sahip bir kaynak sağlıyorsa (örneğin, AFX_IDI_STD_FRAME), MFC bu kaynağı kullanacaktır. Aksi takdirde, varsayılan kaynağı kullanır. Simge için, standart uygulama simgesi kullanılır ve imleç için standart ok imleci kullanılır.

İki simge, tek belge türlerine sahip MDI uygulamalarını destekler: Ana uygulama için bir simge, IIC Document/MDIChild Windows için diğer simge. Farklı simgelerle birden çok belge türü için ek `WNDCLASS`es kaydetmelisiniz veya [CFrameWnd:: LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) işlevini kullanmanız gerekir.

`CFrameWnd::LoadFrame`, ilk parametre `WNDCLASS` olarak belirttiğiniz simge kimliğini ve aşağıdaki standart öznitelikleri kullanarak bir kaydeder:

- sınıf stili: CS_DBLCLKS &#124; CS_HREDRAW &#124; CS_VREDRAW;

- simge AFX_IDI_STD_FRAME

- ok imleci

- COLOR_WINDOW arka plan rengi

Öğesinin istemci alanı **MDICLIENT** penceresi tarafından tamamen kapsamında olduğundan, `CMDIFrameWnd` [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) için arka plan rengi ve imleç değerleri kullanılmaz. Microsoft, altsınıflama **MDICLIENT** penceresini teşvik etmez, mümkünse standart renkleri ve imleç türlerini kullanın.

## <a name="subclassing-and-superclassing-controls"></a>Altsınıflama ve superclassing denetimleri

Bir Windows denetimini (örneğin, [CButton](../mfc/reference/cbutton-class.md)) alt sınıfı veya üst sınıfı yaparsanız, sınıfınız bu denetimin Windows uygulamasında `WNDCLASS` belirtilen öznitelikleri otomatik olarak alır.

## <a name="the-afxregisterwndclass-function"></a>AfxRegisterWndClass Işlevi

MFC, bir pencere sınıfını kaydetmek için yardımcı işlev sağlar. Bir öznitelikler kümesi (pencere sınıfı stili, imleç, arka plan fırçası ve simge) verildiğinde, yapay bir ad oluşturulur ve ortaya çıkan pencere sınıfı kaydedilir. Örneğin,

```
const char* AfxRegisterWndClass(UINT nClassStyle,
    HCURSOR hCursor,
    HBRUSH hbrBackground,
    HICON hIcon);
```

Bu işlev, oluşturulan kayıtlı pencere sınıfı adının geçici bir dizesini döndürür. Bu işlev hakkında daha fazla bilgi için bkz. [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass).

Döndürülen dize, statik dize arabelleğinin geçici bir işaretçisidir. Bir sonraki çağrıya `AfxRegisterWndClass`kadar geçerli olur. Bu dizeyi etrafında tutmak istiyorsanız, bu örnekte olduğu gibi bir [CString](../atl-mfc-shared/using-cstring.md) değişkeninde saklayın:

```
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);

...
CWnd* pWnd = new CWnd;
pWnd->Create(strWndClass, ...);

...
```

`AfxRegisterWndClass`pencere sınıfı kayıt (hatalı parametre veya Windows belleği dışında) başarısız olursa bir [CResourceException](../mfc/reference/cresourceexception-class.md) oluşturur.

## <a name="the-registerclass-and-afxregisterclass-functions"></a>RegisterClass ve AfxRegisterClass Işlevleri

`AfxRegisterWndClass` Sağladığından daha karmaşık bir şey yapmak istiyorsanız, Windows API `RegisterClass` 'sini veya MFC işlevini `AfxRegisterClass`çağırabilirsiniz. [](../mfc/reference/cmdichildwnd-class.md) `Create` [](../mfc/reference/cframewnd-class.md) , CFrameWnd ve cmdictepdwnd işlevleri, ilk parametre olarak Window sınıfı için bir lpszClassName dize adı alır. `CWnd` Kayıtlı pencere sınıfı adını, kaydetmek için kullandığınız yöntemden bağımsız olarak kullanabilirsiniz.

Win32 üzerinde bir dll içinde `AfxRegisterClass` (veya `AfxRegisterWndClass`) kullanılması önemlidir. Win32, DLL tarafından kaydedilen sınıfların kaydını otomatik olarak kaldırmaz, bu nedenle DLL sonlandırıldığında sınıfların kaydını açıkça silmeniz gerekir. Bunun yerine `AfxRegisterClass`kullanarak,siziniçin otomatikolarakişlenir.`RegisterClass` `AfxRegisterClass`DLL 'niz tarafından kaydedilen benzersiz sınıfların bir listesini tutar ve DLL sonlandırıldığında otomatik olarak bunların kaydını siler. Dll 'de kullandığınızda `RegisterClass` , dll sonlandırıldığı zaman tüm sınıfların kaydının kaydedildiğinden emin olmanız gerekir ( [DllMain](/windows/win32/Dlls/dllmain) işlevinizde). Bunun yapılmaması, başka bir istemci `RegisterClass` uygulaması dll 'nizi kullanmayı denediğinde beklenmedik şekilde başarısız olmasına neden olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
