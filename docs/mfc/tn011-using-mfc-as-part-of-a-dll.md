---
title: "TN011: Bir DLL'in bir Parçası Olarak MFC Kullanma"
ms.date: 11/04/2016
helpviewer_keywords:
- _USRDLL symbol
- USRDLLs, compiler switches
- TN011
- DLLs [MFC], linking
- MFC DLLs [MFC], linking regular MFC DLLs to MFC
ms.assetid: 76753e9c-59dc-40f6-b6a7-f6bb9a7c4190
ms.openlocfilehash: 0f4d4e2ed76a0fa5f8f775345fc672a1df055a39
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370432"
---
# <a name="tn011-using-mfc-as-part-of-a-dll"></a>TN011: Bir DLL'in bir Parçası Olarak MFC Kullanma

Bu not, Windows dinamik bağlantı kitaplığı (DLL) parçası olarak MFC kitaplığını kullanmanıza olanak tanıyan normal MFC DL'leri açıklar. Windows DL'lere ve bunları nasıl oluşturabileceğinize aşina olduğunuzu varsayar. MFC kitaplığı uzantıları oluşturabileceğiniz MFC uzantılı DLL'ler hakkında bilgi [için](../mfc/tn033-dll-version-of-mfc.md)Bkz.

## <a name="dll-interfaces"></a>DLL Arayüzleri

normal MFC DL'ler uygulama ve DLL arasındaki arabirimlerin C benzeri işlevlerde veya açıkça dışa aktarılan sınıflarda belirtildiğini varsayar. MFC sınıfı arabirimleri dışa aktarılamaz.

Hem DLL hem de bir uygulama MFC kullanmak istiyorsa, her ikisi nin de MFC kitaplıklarının paylaşılan sürümünü kullanma veya kitaplıkların bir kopyasına statik olarak bağlanma seçeneği vardır. Uygulama ve DLL, MFC kitaplığın standart sürümlerinden birini kullanabilir.

normal MFC DLL'lerin birkaç avantajı vardır:

- DLL kullanan uygulama MFC kullanmak zorunda değildir ve Visual C++ uygulaması olmak zorunda değildir.

- Statik olarak MFC'ye bağlanan normal MFC DL'leri ile DLL'nin boyutu yalnızca kullanılan ve bağlanan MFC ve C çalışma zamanı yordamlarına bağlıdır.

- MFC'ye dinamik olarak bağlanan normal MFC DL'leri ile, MFC'nin paylaşılan sürümünü kullanarak bellekte tasarruf önemli olabilir. Ancak, paylaşılan\<DLs, Mfc*sürümü*>.dll ve Msvvcrt\<*sürümü*>.dll, DLL ile dağıtmak gerekir.

- DLL tasarımı, sınıfların nasıl uygulandığından bağımsızdır. DLL tasarımınız yalnızca istediğiniz API'lere dışa sıcatır. Sonuç olarak, uygulama değişirse, normal MFC DLL'leri hala geçerlidir.

- Hem DLL hem de uygulama MFC kullanıyorsa, MFC'ye statik olarak bağlanan normal MFC DL'leri ile, MFC'nin DLL'den farklı bir sürümünü isteyen uygulamayla ilgili herhangi bir sorun yoktur. MFC kitaplığı statik olarak her DLL veya EXE'ye bağlı olduğundan, hangi sürüme sahip olduğunuza dair hiçbir soru yoktur.

## <a name="api-limitations"></a>API Sınırlamaları

Bazı MFC işlevleri, teknik sınırlamalar nedeniyle veya bu hizmetler genellikle uygulama tarafından sağlandığı için DLL sürümü için geçerli değildir. MFC'nin geçerli sürümünde, geçerli olmayan tek `CWinApp::SetDialogBkColor`işlevdir.

## <a name="building-your-dll"></a>DLL'nizi Oluşturma

MFC'ye statik olarak bağlanan normal MFC DL'leri derlerken, semboller `_USRDLL` tanımlanmalıdır. `_WINDLL` DLL kodunuz da aşağıdaki derleyici anahtarları ile derlenmelidir:

- **/D_WINDLL** derleme anlamına gelen bir DLL için

- **/D_USRDLL** normal bir MFC DLL inşa ettiğinizi belirtir

Ayrıca bu sembolleri tanımlamanız ve MFC'ye dinamik olarak bağlanan normal MFC DLL'lerini derlediğinizde bu derleyici anahtarlarını kullanmanız gerekir. Ayrıca, sembol `_AFXDLL` tanımlanmalı ve DLL kodunuz aşağıdakilerle derlenmelidir:

- **/D_AFXDLL,** MFC'ye dinamik olarak bağlanan düzenli bir MFC DLL inşa ettiğinizi belirtir

Uygulama ve DLL arasındaki arabirimler (API'ler) açıkça dışa aktarılmalıdır. Arayüzlerinizi düşük bant genişliği ne olacak şekilde tanımlamanızı ve yalnızca C arabirimlerini kullanmanızı öneririz. Doğrudan C arabirimlerinin bakımı, daha karmaşık C++ sınıflarından daha kolaydır.

API'lerinizi hem C hem de C++ dosyaları tarafından ekilen ayrı bir üstbilgiye yerleştirin. Örneğin MFC Advanced Concepts örnek [DLLScreenCap'teki](../overview/visual-cpp-samples.md) ScreenCap.h başlığına bakın. İşlevlerinizi dışa aktarmak `EXPORTS` için, bunları modül tanım dosyanızın (. DEF) veya `__declspec(dllexport)` işlev tanımlarınıza ekleyin. Bu `__declspec(dllimport)` işlevleri çalıştırılabilen istemciye almak için kullanın.

MFC'ye dinamik olarak bağlanan normal MFC DLL'lerde tüm dışa aktarılan işlevlerin başında AFX_MANAGE_STATE makroeklemeniz gerekir. Bu makro, geçerli modül durumunu DLL için olana ayarlar. Bu makroyu kullanmak için, DLL'den dışa aktarılan işlevlerin başına aşağıdaki kod satırını ekleyin:

`AFX_MANAGE_STATE(AfxGetStaticModuleState( ))`

## <a name="winmain---dllmain"></a>WinMain -> DllMain

MFC kitaplığı, [CWinApp](../mfc/reference/cwinapp-class.md) `DllMain` türetilmiş nesnenizi tipik bir MFC uygulamasında olduğu gibi ilk olarak açan standart Win32 giriş noktasını tanımlar. Tüm DLL'ye özgü başlatmayı, tipik bir MFC uygulamasında olduğu gibi [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) yöntemine yerleştirin.

[CWinApp::Çalıştır](../mfc/reference/cwinapp-class.md#run) mekanizması dll için geçerli değildir, çünkü uygulama ana mesaj pompasına sahip olur. DLL'niz modeless iletişim noktalarını görüntülerse veya kendi ana çerçeve penceresi varsa, uygulamanızın ana ileti pompası [CWinApp::PreTranslateMessage](../mfc/reference/cwinapp-class.md#pretranslatemessage)çağıran bir DLL dışa aktarılan yordamı çağırmalıdır.

Bu işlevin kullanımı için DLLScreenCap örneğine bakın.

MFC'nin `DllMain` sağladığı işlev, DLL kaldırılmadan `CWinApp` önce türetilen sınıfınızın [CWinApp::ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) yöntemini çağırır.

## <a name="linking-your-dll"></a>DLL'nizi Bağlama

MFC'ye statik olarak bağlanan normal MFC DL'ler ile DLL'nizi Nafxcwd.lib veya Nafxcw.lib ile ve Libcmt.lib adlı C çalışma saatlerinin sürümüne bağlamanız gerekir. Bu kitaplıklar önceden oluşturulmuştur ve Visual C++ kurulumlarını çalıştırdığınızda belirterek yüklenebilir.

## <a name="sample-code"></a>Örnek Kod

Tam bir örnek için MFC Advanced Concepts örnek programı DLLScreenCap'e bakın. Bu örnekte dikkat edilmesi gereken birkaç ilginç şey aşağıdaki gibidir:

- DLL ve uygulamanın derleyici bayrakları farklıdır.

- Bağlantı çizgileri ve. DLL için DEF dosyaları ve uygulama için olanlar farklıdır.

- DLL kullanan uygulama C++'da olmak zorunda değildir.

- Uygulama ve DLL arasındaki arabirim, C veya C++ tarafından kullanılabilir ve DLLScreenCap.def ile dışa aktarılan bir API'dir.

Aşağıdaki örnekte, mfc'ye statik olarak bağlanan normal bir MFC DLL'de tanımlanan bir API gösteriş yapılır. Bu örnekte, bildirim C++ `extern "C" { }` kullanıcıları için bir blok içinde eklenir. Bunun birkaç avantajı vardır. İlk olarak, DLL API'lerinizi C++ olmayan istemci uygulamaları tarafından kullanılabilir hale getirir. İkinci olarak, C++ adı mangling dışa aktarılan ada uygulanmaz, çünkü DLL yükü azaltır. Son olarak, açıkça bir . DEF dosyası (ordinal tarafından dışa aktarmak için) isim mangling hakkında endişelenmenize gerek kalmadan.

```cpp
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

API tarafından kullanılan yapılar MFC sınıflarından türetilmiş değildir ve API üstbilgisinde tanımlanır. Bu, DLL ve uygulama arasındaki arabirimin karmaşıklığını azaltır ve DLL'yi C programları tarafından kullanılabilir hale getirir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
