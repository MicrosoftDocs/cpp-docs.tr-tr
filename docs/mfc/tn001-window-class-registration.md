---
title: 'TN001: Pencere Sınıfı Kaydı'
ms.date: 11/04/2016
f1_keywords:
- vc.registration
helpviewer_keywords:
- TN001
- WNDCLASS [MFC]
- AfxRegisterClass function
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
ms.openlocfilehash: 92d55780ad309a9c8392cf86e7fa4eaefc5f407a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619160"
---
# <a name="tn001-window-class-registration"></a>TN001: Pencere Sınıfı Kaydı

Bu Not özel kayıt MFC yordamları açıklar [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576)es Microsoft Windows tarafından gerekli. Belirli `WNDCLASS` MFC ve Windows tarafından kullanılan öznitelikler ele alınmıştır.

## <a name="the-problem"></a>Sorun

Öznitelikleri bir [CWnd](../mfc/reference/cwnd-class.md) nesne gibi bir `HWND` işlemek Windows, iki yerde depolanır: pencere nesnesi ve `WNDCLASS`. Adını `WNDCLASS` gibi genel pencere oluşturma işleve geçirilen [CWnd::Create](../mfc/reference/cwnd-class.md#create) ve [CFrameWnd::Create](../mfc/reference/cframewnd-class.md#create) içinde *lpszClassName* parametresi.

Bu `WNDCLASS` dört biri aracılığıyla kayıtlı olması gerekir:

- Sağlanan bir MFC kullanarak örtük olarak `WNDCLASS`.

- Örtük olarak bir Windows Denetim (veya başka bir denetimde) sınıflara göre.

- MFC çağırarak açıkça [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) veya [AfxRegisterClass](../mfc/reference/application-information-and-management.md#afxregisterclass).

- Windows yordam çağırarak açıkça [RegisterClass](https://msdn.microsoft.com/library/windows/desktop/ms633586).

## <a name="wndclass-fields"></a>WNDCLASS alanları

`WNDCLASS` Yapısı pencere sınıfı tanımlayan çeşitli alanları içerir. Aşağıdaki tablo alanları gösterir ve bir MFC uygulamasında nasıl kullanılacağını belirtir:

|Alan|Açıklama|
|-----------|-----------------|
|*lpfnWndProc*|Pencere işleme olmalıdır bir `AfxWndProc`|
|*cbClsExtra*|kullanılmayan (sıfır olmalıdır)|
|*cbWndExtra*|kullanılmayan (sıfır olmalıdır)|
|*HINSTANCE*|otomatik olarak doldurulmuş [Afxgetınstancehandle](../mfc/reference/application-information-and-management.md#afxgetinstancehandle)|
|*hIcon*|simge çerçeve pencereleri için aşağıya bakın|
|*hCursor*|İmleç fare pencere üzerinde olduğunda için aşağıya bakın|
|*hbrBackground*|arka plan rengi, aşağıya bakın|
|*lpszMenuName*|kullanılmayan (NULL olmalıdır)|
|*lpszClassName*|sınıf adı, aşağıya bakın|

## <a name="provided-wndclasses"></a>WNDCLASSes sağlanan

Önceki sürümlerdeki MFC (önce MFC 4.0), önceden tanımlanmış çeşitli pencere sınıfları sağlanır. Bu pencere sınıflarının artık varsayılan olarak sağlanır. Uygulamaların kullanması gereken `AfxRegisterWndClass` uygun parametrelerle.

Belirtilen kaynak kimliği (örneğin, AFX_IDI_STD_FRAME) sahip bir kaynak uygulama sağlar, MFC, kaynak kullanır. Aksi takdirde varsayılan kaynak kullanır. Simge için kullanılan standart uygulama simgesi ve imleci için standart ok imleci kullanılır.

İki simgeyi MDI uygulamaları ile tek bir belge türlerini destekler: ana uygulama için bir simge, diğer icon belge/MDIChild windows simgesi. Farklı simgeleri içeren birden çok belge türü için ek kaydetmeniz gerekir `WNDCLASS`vet veya kullanım [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) işlevi.

`CFrameWnd::LoadFrame` Kaydolacak bir `WNDCLASS` ilk parametre ve şu standart öznitelikleri belirttiğiniz simge Kimliğini kullanarak:

- sınıf stili: CS_DBLCLKS &#124; CS_HREDRAW &#124; CS_VREDRAW;

- AFX_IDI_STD_FRAME simgesi

- İmleç oku

- COLOR_WINDOW arka plan rengi

Arka plan rengi ve imleci için değerleri [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) beri istemci alanının kullanılmaz `CMDIFrameWnd` tamamen kapsamına giren **MDICLIENT** penceresi. Microsoft, sınıflara teşvik değil **MDICLIENT** penceresi kadar standart renkler ve işaretçi türleri mümkün olduğunda kullanın.

## <a name="subclassing-and-superclassing-controls"></a>Sınıflara ve Superclassing denetimleri

Alt veya üst bir Windows denetimini varsa (örneğin, [CButton](../mfc/reference/cbutton-class.md)) sınıfınıza otomatik olarak alır, ardından `WNDCLASS` denetleyen Windows uygulamasında sağlanan öznitelikleri.

## <a name="the-afxregisterwndclass-function"></a>AfxRegisterWndClass işlevi

MFC pencere sınıfı kaydetmek için yardımcı işlevini sağlar. Bir dizi öznitelikleri (pencere sınıfı stili, imleç, arka plan Fırçası ve simgesi) göz önünde bulundurulduğunda, yapay bir ad oluşturulur ve elde edilen pencere sınıfını kaydedilir. Örneğin,

```
const char* AfxRegisterWndClass(UINT nClassStyle,
    HCURSOR hCursor,
    HBRUSH hbrBackground,
    HICON hIcon);
```

Bu işlev, oluşturulan kayıtlı pencere sınıf adı, geçici bir dize döndürür. Bu işlev hakkında daha fazla bilgi için bkz. [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass).

Döndürülen dize, bir statik dize arabellek için geçici bir işaretçisidir. Sonraki çağrı kadar geçerli olduğundan `AfxRegisterWndClass`. Bu dize etrafında tutmak istiyorsanız, depoladığınız bir [CString](../atl-mfc-shared/using-cstring.md) Bu örnekte olduğu gibi değişken:

```
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);

...
CWnd* pWnd = new CWnd;
pWnd->Create(strWndClass, ...);

...
```

`AfxRegisterWndClass` oluşturur bir [CResourceException](../mfc/reference/cresourceexception-class.md) pencere sınıfını (ya da geçersiz parametreler nedeniyle veya Windows bellek yetersiz) kaydedilemedi durumunda.

## <a name="the-registerclass-and-afxregisterclass-functions"></a>AfxRegisterClass işlevleri ve RegisterClass

Yapmak istiyorsanız herhangi bir şey daha ne karmaşık `AfxRegisterWndClass` sağlar, Windows API çağırmak `RegisterClass` veya MFC işlevi `AfxRegisterClass`. `CWnd`, [CFrameWnd](../mfc/reference/cframewnd-class.md) ve [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md) `Create` işlevler bir *lpszClassName* pencere sınıf birinci parametre olarak dize adı. Kaydetmek için kullanılan yöntem ne olursa olsun, tüm kayıtlı Windows sınıf adı kullanabilirsiniz.

Kullanmak önemlidir `AfxRegisterClass` (veya `AfxRegisterWndClass`) bir Win32 DLL içinde. Win32 DLL sonlandırıldığında sınıfları açıkça kaydını silmeniz gerekir, böylece bir DLL tarafından kayıtlı sınıfları otomatik olarak kaydını değil. Kullanarak `AfxRegisterClass` yerine `RegisterClass` bu otomatik olarak sizin yerinize gerçekleştirilir. `AfxRegisterClass` benzersiz sınıfları listesi, DLL tarafından kaydedilmiş ve DLL sonlandığında otomatik olarak bunları kaldıran korur. Kullanırken `RegisterClass` bir DLL içinde DLL sonlandırıldığında tüm sınıflar kaydı olmasına dikkat edin (içinde [DllMain](/windows/desktop/Dlls/dllmain) işlevi). Bunun yapılmaması neden olabilecek `RegisterClass` başka bir istemci uygulaması, DLL dosyanızı kullanmayı dener beklenmedik şekilde başarısız.

## <a name="see-also"></a>Ayrıca Bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

