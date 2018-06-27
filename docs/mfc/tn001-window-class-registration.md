---
title: 'TN001: Pencere sınıfı kaydı | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.registration
dev_langs:
- C++
helpviewer_keywords:
- TN001
- WNDCLASS [MFC]
- AfxRegisterClass function
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e0be2e87f77e047e1b29d99e562a67bb9f4f1ee9
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951984"
---
# <a name="tn001-window-class-registration"></a>TN001: Pencere Sınıfı Kaydı
Bu Not özel kaydetmek MFC yordamları açıklar [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)es Microsoft Windows tarafından gerekli. Belirli `WNDCLASS` MFC ve Windows tarafından kullanılan öznitelikleri ele alınmıştır.  
  
## <a name="the-problem"></a>Sorun  
 Öznitelikleri bir [CWnd](../mfc/reference/cwnd-class.md) nesne gibi bir `HWND` Windows işlemek, iki yerde depolanır: pencere nesnesi ve `WNDCLASS`. Adını `WNDCLASS` genel pencere oluşturma işlevlere gibi geçirilen [CWnd::Create](../mfc/reference/cwnd-class.md#create) ve [CFrameWnd::Create](../mfc/reference/cframewnd-class.md#create) içinde *lpszClassName* parametresi.  
  
 Bu `WNDCLASS` dört anlamına gelir biri aracılığıyla kayıtlı olması gerekir:  
  
-   Sağlanan bir MFC kullanarak örtük olarak `WNDCLASS`.  
  
-   Örtük olarak bir Windows denetimini (veya başka bir denetim) sınıflara göre.  
  
-   MFC çağırarak açıkça [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) veya [AfxRegisterClass](../mfc/reference/application-information-and-management.md#afxregisterclass).  
  
-   Windows yordamını çağırarak açıkça [RegisterClass](http://msdn.microsoft.com/library/windows/desktop/ms633586).  
  
## <a name="wndclass-fields"></a>WNDCLASS alanları  
 `WNDCLASS` Yapısı pencere sınıfı tanımlayan çeşitli alanları oluşur. Aşağıdaki tabloda alanları gösterir ve bir MFC uygulamasında nasıl kullanıldıkları belirtir:  
  
|Alan|Açıklama|  
|-----------|-----------------|  
|*lpfnWndProc*|Pencere proc olmalıdır bir `AfxWndProc`|  
|*cbClsExtra*|kullanılmayan (sıfır olmalıdır)|  
|*cbWndExtra*|kullanılmayan (sıfır olmalıdır)|  
|*HINSTANCE*|otomatik olarak girilmiş [Afxgetınstancehandle](../mfc/reference/application-information-and-management.md#afxgetinstancehandle)|  
|*hIcon*|Çerçeve pencereleri simge bkz aşağıda|  
|*hCursor*|Fare pencere üzerinde olduğunda için imleç bkz aşağıda|  
|*hbrBackground*|arka plan rengi, aşağıya bakın|  
|*lpszMenuName*|kullanılmayan (NULL olmalıdır)|  
|*lpszClassName*|sınıf adı, aşağıya bakın|  
  
## <a name="provided-wndclasses"></a>WNDCLASSes sağlanan  
 MFC (MFC 4.0), uygulamadan önce önceki sürümlerinde sağlanan önceden tanımlanmış birkaç pencere sınıfları. Bu pencere sınıfları artık varsayılan olarak sağlanır. Uygulamaları kullanması gereken `AfxRegisterWndClass` uygun parametrelerle.  
  
 MFC Uygulama belirtilen kaynak kimliği (örneğin, AFX_IDI_STD_FRAME) sahip bir kaynak sağlıyorsa, o kaynak kullanır. Aksi takdirde, varsayılan kaynak kullanır. Simge için standart uygulama simge kullanılır ve standart ok imleç imleci için kullanılır.  
  
 İki simgeler tek bir belge türleriyle MDI uygulamaları destekler: ana uygulama için bir simge, simge belge MDIChild windows diğer simgesi. Farklı simgelere sahip birden çok belge türü için ek kaydetmeniz gerekir `WNDCLASS`es veya kullanım [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) işlevi.  
  
 `CFrameWnd::LoadFrame` kaydedilecek bir `WNDCLASS` ilk parametre ve aşağıdaki standart özniteliklerini belirttiğiniz simgesi Kimliğini kullanarak:  
  
-   sınıf stili: CS_DBLCLKS &#124; CS_HREDRAW &#124; CS_VREDRAW;  
  
-   simge AFX_IDI_STD_FRAME  
  
-   ok imleç  
  
-   COLOR_WINDOW arka plan rengi  
  
 Arka plan rengi ve imleci için değerlerini [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) bu yana istemci alanını kullanılmaz `CMDIFrameWnd` tamamen tarafından kapsanan **MDICLIENT** penceresi. Microsoft sınıflara teşvik değil **MDICLIENT** penceresini kullanın standart renkleri ve imleç türleri mümkün olduğunda.  
  
## <a name="subclassing-and-superclassing-controls"></a>Sınıflara ve üst Sınıflama denetimleri  
 Bir alt veya üst sınıf bir Windows denetimini varsa (örneğin, [CButton](../mfc/reference/cbutton-class.md)) sınıfınız otomatik olarak alır sonra `WNDCLASS` denetleyen Windows uygulamasında sağlanan öznitelikler.  
  
## <a name="the-afxregisterwndclass-function"></a>AfxRegisterWndClass işlevi  
 MFC pencere sınıfı kaydı için yardımcı bir işlev sağlar. Öznitelikler (pencere sınıfı stili, imleç, arka plan Fırçası ve simgesi) kümesi verildiğinde, yapay bir ad oluşturulur ve sonuçta elde edilen pencere sınıfı kaydedilir. Örneğin,  
  
```  
const char* AfxRegisterWndClass(UINT nClassStyle,
    HCURSOR hCursor,
    HBRUSH hbrBackground,
    HICON hIcon);
```  
  
 Bu işlev oluşturulan kayıtlı pencere sınıf adının geçici bir dize döndürür. Bu işlev hakkında daha fazla bilgi için bkz: [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass).  
  
 Döndürülen dize statik dizesi arabelleği geçici bir işaretçidir. Sonraki çağrı kadar geçerli olduğundan `AfxRegisterWndClass`. Bu dize geçici tutmak istiyorsanız, bunu depolamak bir [CString](../atl-mfc-shared/using-cstring.md) Bu örnekte olduğu gibi değişkeni:  
  
```  
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);

...  
CWnd* pWnd = new CWnd;  
pWnd->Create(strWndClass, ...);

...  
```  
  
 `AfxRegisterWndClass` özel durum oluşturacak bir [CResourceException](../mfc/reference/cresourceexception-class.md) pencere sınıfı (hatalı parametre nedeniyle ya da Windows bellek yetersiz) kaydetmek başarısız olduysa.  
  
## <a name="the-registerclass-and-afxregisterclass-functions"></a>RegisterClass ve AfxRegisterClass işlevleri  
 Yapmak istiyorsanız, her şeyi daha ne Gelişmiş bir `AfxRegisterWndClass` sağlar, Windows API'si çağırabilirsiniz `RegisterClass` veya MFC işlevi `AfxRegisterClass`. `CWnd`, [CFrameWnd](../mfc/reference/cframewnd-class.md) ve [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md) `Create` işlevleri ele bir *lpszClassName* ilk parametre olarak pencere sınıfı için dize adı. Kaydetmek için kullanılan yöntem bağımsız olarak tüm kayıtlı pencere sınıfı adı kullanabilirsiniz.  
  
 Kullanmak önemlidir `AfxRegisterClass` (veya `AfxRegisterWndClass`) Win32 üzerinde DLL'de. Win32 DLL sonlandırıldığında sınıfları açıkça kayıttan çıkarmanız gerekir böylece bir DLL tarafından kayıtlı sınıflarını otomatik olarak kaydını değil. Kullanarak `AfxRegisterClass` yerine `RegisterClass` bu otomatik olarak sizin için işlenir. `AfxRegisterClass` benzersiz sınıflarının bir listesini, DLL tarafından kaydedilen ve DLL sonlandırıldığında otomatik olarak onları kaldırır korur. Kullandığınızda `RegisterClass` DLL'de, DLL sonlandırıldığında tüm sınıflar kaydı olmasına dikkat edin (içinde [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583) işlevi). Bunun Sağlanamaması neden olabilecek `RegisterClass` başka bir istemci uygulama, DLL kullanma girişiminde bulunduğunda beklenmedik şekilde başarısız.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

