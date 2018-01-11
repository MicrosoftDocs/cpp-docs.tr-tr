---
title: "TN011: Bir DLL'in bir parçası MFC kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.dll
dev_langs: C++
helpviewer_keywords:
- _USRDLL symbol
- USRDLLs, compiler switches
- TN011
- DLLs [MFC], linking
- MFC DLLs [MFC], linking regular MFC DLLs to MFC
ms.assetid: 76753e9c-59dc-40f6-b6a7-f6bb9a7c4190
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0d0ac05e314f3f8354ba289695afa672b1e28881
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tn011-using-mfc-as-part-of-a-dll"></a>TN011: Bir DLL'in bir Parçası Olarak MFC Kullanma
Bu Not MFC kitaplığını Windows dinamik bağlantı kitaplığı (DLL) bir parçası olarak kullanmanıza olanak sağlayan Normal MFC DLL'leri açıklar. Bu, Windows DLL'leri ve bunları oluşturma konusunda bilgi sahibi olduğunuzu varsayar. MFC uzantı DLL'leri hakkında daha fazla bilgi için hangi oluşturabileceğiniz ile MFC kitaplığına uzantılarını görmek [, DLL sürümü MFC](../mfc/tn033-dll-version-of-mfc.md).  
  
## <a name="dll-interfaces"></a>DLL arabirimleri  
 arabirimler uygulama ve DLL arasında C benzeri işlevler veya açıkça dışarı aktarılan sınıfları belirtilen Normal MFC DLL'leri varsayalım. MFC sınıf arabirimleri verilemez.  
  
 DLL ve uygulama MFC kullanmak istiyorsanız hem ya da MFC kitaplıkları paylaşılan sürümü kullanmak için veya bir kopyasını kitaplıkları için statik olarak bağlamak için bir seçenek sahiptir. Uygulama ve DLL hem standart MFC kitaplık sürümleri birini kullanabilirsiniz.  
  
 Normal MFC DLL'leri çeşitli avantajları vardır:  
  
-   DLL kullanan uygulama MFC kullanmak zorunda değildir ve bir Visual C++ uygulaması olması gerekmez.  
  
-   Normal MFC statik olarak MFC'ye DLL'leri ile DLL kullanılan ve bağlı yalnızca MFC ve C çalışma zamanı yordamları üzerinde boyutuna bağlıdır.  
  
-   Normal MFC dinamik olarak MFC'ye DLL'leri ile MFC paylaşılan sürümünü kullanarak bellekte tasarruf önemli olabilir. Bununla birlikte, paylaşılan DLL'ler, Mfc dağıtmalısınız*\<sürüm >*.dll ve Msvvcrt*\<sürüm >*DLL ile .dll.  
  
-   DLL tasarım sınıfları nasıl uygulandığını bağımsızdır. DLL tasarımınızı istediğiniz API'leri yalnızca dışa aktarır. Sonuç olarak, uygulama değişirse, Normal MFC DLL'leri hala geçerli.  
  
-   Statik olarak MFC'ye, bağlantı Normal MFC DLL'leri ile MFC DLL ve uygulama kullanırsanız, MFC DLL daha veya farklı bir sürümü istiyorsa uygulama ile herhangi bir sorun vardır. MFC Kitaplığı her bir DLL veya EXE statik olarak bağlantılı olduğundan, elinizde hangi sürümü hakkında bir soru yok yok.  
  
## <a name="api-limitations"></a>API sınırlamaları  
 MFC işlevselliğinin teknik sınırlamaları nedeniyle ya da DLL sürümü için geçerli değildir veya bu hizmetlerin genellikle uygulama tarafından sağlanır. MFC geçerli sürümü ile geçerli değil yalnızca işlevidir `CWinApp::SetDialogBkColor`.  
  
## <a name="building-your-dll"></a>DLL oluşturma  
 Statik olarak MFC'ye, simgeler bağlantı Normal MFC DLL derlenirken `_USRDLL` ve `_WINDLL` tanımlanması gerekir. DLL kodunuzu ayrıca aşağıdaki derleyici anahtarları ile derlenmiş gerekir:  
  
- **/ D_WINDLL** derleme bir DLL için olduğunu belirtir  
  
- **/ D_USRDLL** normal bir MFC DLL oluşturduğunuz belirtir  
  
 Ayrıca bu simgeleri tanımlayın ve dinamik olarak MFC'ye Normal MFC DLL'leri derlediğinizde Bu derleyici anahtarları kullanmanız gerekir. Ayrıca, simge `_AFXDLL` tanımlanmalıdır ve DLL kodunuzu ile derlenmiş gerekir:  
  
- **/ D_AFXDLL** dinamik olarak MFC'ye bağlanan normal bir MFC DLL oluşturma belirtir  
  
 Uygulama ve DLL arasında arabirimleri (API) açıkça verilmelidir. Düşük bant genişliğine sahip olacak şekilde arabirimlerinizi tanımlama ve yapabiliyorsanız yalnızca C arabirimleri kullanma öneririz. Doğrudan C arabirimleri daha karmaşık C++ sınıfları bakımı daha kolay olur.  
  
 C ve C++ dosyaları tarafından eklenebilir ayrı bir üstbilgi Apı'lerinizi koyun. MFC Gelişmiş kavramları örnek ScreenCap.h üstbilgisinde bkz [ile ilgili](../visual-cpp-samples.md) bir örnek. İşlevlerinizi dışarı aktarmak için bunları girin `EXPORTS` bölümünde modül tanım dosyası (. DEF) veya dahil `__declspec(dllexport)` işlev tanımları üzerinde. Kullanım `__declspec(dllimport)` bu işlevler yürütülebilir istemcisine içeri aktarmak için.  
  
 Eklemelisiniz `AFX_MANAGE_STATE` makrosu dinamik olarak MFC'ye Normal MFC DLL'leri dışarı aktarılan işlevler başındaki. Bu makrosu DLL için geçerli modül durumunu ayarlar. Bu makrosu kullanmak için DLL'den dışarı aktarılan işlevlerin başına aşağıdaki kod satırını ekleyin:  
  
 `AFX_MANAGE_STATE(AfxGetStaticModuleState( ))`  
  
## <a name="winmain---dllmain"></a>WinMain DllMain ->  
 MFC kitaplığını standart Win32 tanımlar `DllMain` başlatır giriş noktası, [CWinApp](../mfc/reference/cwinapp-class.md) türetilmiş nesnesinin tipik bir MFC uygulaması olduğu gibi. Tüm DLL özgü başlatma yerleştirin [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) tipik bir MFC uygulaması yönteminizdeki.  
  
 Unutmayın [CWinApp::Run](../mfc/reference/cwinapp-class.md#run) mekanizması uygulamanın ana ileti göndericisi olduğundan bir DLL için uygulanmaz. DLL kalıcı olmayan iletişim kutuları görüntüler ya da kendi ana penceresi varsa, uygulamanızın ana ileti göndericisi çağıran DLL dışarı aktarılan bir yordam çağırmalıdır [CWinApp::PreTranslateMessage](../mfc/reference/cwinapp-class.md#pretranslatemessage).  
  
 Bu işlev kullanımı ile ilgili örnek bakın.  
  
 `DllMain` Çağıracaktır MFC sağlar işlevi [CWinApp::ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) yöntemi sınıfınızın türetildiği `CWinApp` DLL kaldırılmadan önce.  
  
## <a name="linking-your-dll"></a>DLL bağlama  
 Normal MFC statik olarak MFC'ye DLL'leri ile DLL Nafxcwd.lib veya Nafxcw.lib ve Libcmt.lib adlı C çalışma zamanları sürümü ile bağlamanız gerekir. Bu kitaplıklar, önceden oluşturulmuş ve Visual C++ Kurulumu çalıştırdığınızda bunları belirterek yüklü olabilir.  
  
## <a name="sample-code"></a>Örnek kod  
 İle ilgili tam bir örnek için program MFC Gelişmiş kavramları örneğine bakın. Bu örnekte dikkat edilecek birkaç ilginç noktalar aşağıdaki gibidir:  
  
-   DLL derleyici bayraklarını ve bu uygulamanın farklıdır.  
  
-   Bağlantı çizgileri ve. DEF dosyaları DLL için ve bu uygulama için farklıdır.  
  
-   DLL kullanan uygulama C++'da olmak zorunda değildir.  
  
-   C veya C++ tarafından kullanılabilir ve dışa aktarılan bir API DLLScreenCap.def ile uygulama ve DLL arasındaki arabirimdir.  
  
 Aşağıdaki örnek, normal MFC'ye MFC DLL tanımlanan bir API gösterilmektedir. Bu örnekte, bildirimi sınırlanan bir `extern "C" { }` C++ kullanıcıları için bloğu. Bu, çeşitli avantajları vardır. İlk olarak, DLL Apı'lerinizi kullanılabilir C++ dışı istemci uygulamaları tarafından kolaylaştırır. İkinci olarak, ad C++ bozma dışarı aktarılan adına uygulanmaz çünkü DLL ek yükünü azaltır. Son olarak, açıkça eklemek kolaylaştırır bir. DEF dosya (sıralı olarak dışa aktarmak için) ad bozma hakkında endişelenmeye gerek kalmadan.  
  
```  
#ifdef __cplusplus  
extern "C" {  
#endif  /* __cplusplus */  
 
struct TracerData  
{  
    BOOL bEnabled;  
    UINT flags;  
};  
 
BOOL PromptTraceFlags(TracerData FAR* lpData);

 
#ifdef __cplusplus  
}  
#endif  
```  
  
 API tarafından kullanılan yapılar MFC sınıfları türetilmemiş ve API başlığında tanımlanır. Bu DLL ve uygulama arasındaki arabirim karmaşıklığını azaltır ve DLL C programlar tarafından kullanılabilir hale getirir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

