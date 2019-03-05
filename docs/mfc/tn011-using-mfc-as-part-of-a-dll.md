---
title: "TN011: Bir DLL'in bir parçası MFC kullanma"
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.dll
helpviewer_keywords:
- _USRDLL symbol
- USRDLLs, compiler switches
- TN011
- DLLs [MFC], linking
- MFC DLLs [MFC], linking regular MFC DLLs to MFC
ms.assetid: 76753e9c-59dc-40f6-b6a7-f6bb9a7c4190
ms.openlocfilehash: 63e97c3b9260465259d76cf6996d1d389f65ee41
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326458"
---
# <a name="tn011-using-mfc-as-part-of-a-dll"></a>TN011: Bir DLL'in bir parçası MFC kullanma

Bu Not, MFC kitaplığını Windows dinamik bağlantı kitaplığı (DLL) bir parçası olarak kullanmanıza olanak sağlayan Normal MFC DLL'leri açıklar. Bu, Windows DLL'leri ve bunları oluşturma konusunda bilgi sahibi olduğunuzu varsayar. MFC uzantı DLL'leri hakkında daha fazla bilgi için oluşturabileceğiniz ile MFC Kitaplığı için uzantıları bakın [MFC DLL sürümü](../mfc/tn033-dll-version-of-mfc.md).

## <a name="dll-interfaces"></a>DLL arabirimi

Normal MFC DLL'leri C gibi işlevleri veya açıkça dışa aktarılan sınıfları arabirimler uygulama ve DLL arasında belirtilen varsayılır. MFC sınıf arabirimleri dışarı aktarılamaz.

Bir DLL hem uygulamanın MFC kullanmak istiyorsanız, her ikisini ya da MFC kitaplıkları paylaşılan sürümünü kullanın veya bir kopyasını kitaplıkları için kitaplıklarla statik bağlantılar oluşturabilir vardır. Uygulama ve DLL hem MFC Kitaplığı'nın standard sürümlerinden birini kullanabilir.

Normal MFC DLL'leri çeşitli avantajları vardır:

- DLL kullanan uygulama MFC kullanmak zorunda değildir ve Visual C++ uygulaması olması gerekmez.

- Normal MFC, MFC DLL'lerine DLL'ler ile kullanılan ve bağlı olan yalnızca MFC ve C çalışma zamanı yordamları üzerinde DLL boyutuna bağlıdır.

- Normal MFC dinamik olarak MFC'ye bağlanan DLL'ler ile tasarruf kullanarak MFC'nin paylaşılan sürümünden belleğe önemli olabilir. Bununla birlikte, paylaşılan dll, Mfc dağıtmanız gerekir\<*sürüm*> .dll ve Msvvcrt\<*sürüm*> .dll, DLL dosyanız ile.

- DLL tasarım sınıfları nasıl uygulandığını bağımsızdır. DLL tasarımınızı istediğiniz API'leri yalnızca dışarı aktarır. Sonuç olarak, uygulama değişirse, Normal MFC DLL'leri hala geçerli.

- MFC'ye statik olarak bağlanan normal MFC DLL'leri ile MFC DLL hem uygulama kullanırsanız, MFC DLL veya tam tersi farklı bir sürümü istiyorsa uygulama ile herhangi bir sorun vardır. MFC Kitaplığı her bir DLL veya EXE statik olarak bağlı olduğundan elinizde hangi sürümü hakkında bir soru yok.

## <a name="api-limitations"></a>API sınırlamaları

DLL sürümü, ya da teknik sınırlamaları nedeniyle bazı MFC işlevleri uygulanmaz veya bu hizmetleri genellikle uygulama tarafından sağlanır. MFC geçerli sürümü ile geçerli değil yalnızca işlevidir `CWinApp::SetDialogBkColor`.

## <a name="building-your-dll"></a>DLL oluşturma

MFC, simgeler statik olarak bağlanan normal MFC DLL'leri derlenirken `_USRDLL` ve `_WINDLL` tanımlanması gerekir. DLL kodunuzu ayrıca aşağıdaki derleyici anahtarları ile derlenmiş olmalıdır:

- **/ D_WINDLL** derleme bir DLL için olduğunu belirtir

- **/ D_USRDLL** Normal MFC DLL'SİNİN oluşturuyor olduğunuz belirtir

Ayrıca bu sembolleri tanımlayın ve bu derleyici anahtarları, dinamik olarak MFC'ye bağlanan normal MFC DLL'leri derlerken kullanmanız gerekir. Ayrıca, sembol `_AFXDLL` tanımlanmalıdır ve DLL kodunuzu ile derlenmelidir:

- **/ D_AFXDLL** dinamik olarak MFC'ye bağlı normal MFC DLL'SİNİN oluşturulmasını belirtir

' % S'arabirimleri (API) uygulama ve DLL arasında açıkça verilmelidir. Düşük bant genişliği olacak şekilde, arabirimler tanımlar ve yalnızca C arabirimleri yapabiliyorsanız kullanın öneririz. Doğrudan C arabirimleri korumak daha karmaşık C++ sınıfları kolaydır.

Apı'lerinizi hem C hem de C++ dosyaları dahil edilebilmesi için ayrı bir üstbilgi yerleştirin. MFC Gelişmiş kavramlar örneği üstbilgisinde ScreenCap.h bkz [ile ilgili](../visual-cpp-samples.md) örneği. İşlevlerinizi dışarı aktarmak için bunları girin `EXPORTS` bölümünü, modül tanım dosyası (. DEF) veya dahil `__declspec(dllexport)` , işlev tanımları üzerinde. Kullanım `__declspec(dllimport)` bu işlevler yürütülebilir istemci içeri aktarmak için.

Dinamik olarak MFC'ye bağlanan normal MFC DLL'leri dışarı aktarılan işlevlerin başında AFX_MANAGE_STATE makrosuna eklemeniz gerekir. Bu makro, bir DLL için geçerli modül durumunu ayarlar. Bu makroyu kullanmak için işlevleri bir DLL'den dışarı başlangıcına aşağıdaki kod satırını ekleyin:

`AFX_MANAGE_STATE(AfxGetStaticModuleState( ))`

## <a name="winmain---dllmain"></a>WinMain DllMain ->

MFC Kitaplığı standart Win32 tanımlar `DllMain` başlatır giriş noktası, [CWinApp](../mfc/reference/cwinapp-class.md) türetilmiş bir nesneye tipik bir MFC uygulaması olduğu gibi. Tüm DLL'ye özgü başlatmada yerleştirin [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) yöntemi tipik bir MFC uygulaması olduğu gibi.

Unutmayın [CWinApp::Run](../mfc/reference/cwinapp-class.md#run) mekanizması uygulamanın ana ileti göndericisi çünkü bir DLL için uygulanmaz. DLL'niz kalıcı olmayan iletişim kutuları görüntüler veya kendi ana penceresi, uygulamanızın ana ileti pompası çağıran bir DLL dışarı yordam çağırmalıdır [CWinApp::PreTranslateMessage](../mfc/reference/cwinapp-class.md#pretranslatemessage).

Bu işlev kullanım ile ilgili örnek bakın.

`DllMain` Çağıracaktır MFC sağlayan işlev [CWinApp::ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) yöntemi türetilmiş sınıfınızın `CWinApp` DLL kaldırılmadan önce.

## <a name="linking-your-dll"></a>DLL bağlama

Normal MFC, MFC DLL'lerine DLL'ler ile DLL dosyanızı Nafxcwd.lib veya Nafxcw.lib ve LIBCMT.lib adlı C çalışma zamanı sürümü ile bağlanması gerekir. Bu kitaplıklar, önceden oluşturulmuş ve Visual C++ Kurulum'u çalıştırdığınızda bunları belirterek yüklenebilir.

## <a name="sample-code"></a>Örnek Kod

MFC Gelişmiş kavramlar örneği ile ilgili eksiksiz bir örnek için program bakın. Bu örnekte dikkat edilecek bazı ilgi çekici noktalar aşağıdaki gibidir:

- Derleyici bayraklarına dll ve bu uygulamanın farklıdır.

- Çizgileri ve. DEF dosyaları DLL için ve bu uygulama için farklıdır.

- DLL kullanan uygulama c++'ta olması gerekmez.

- C veya C++ tarafından kullanılabilir ve dışa aktarılan bir API DLLScreenCap.def ile uygulama ve DLL arasında arabirimidir.

Aşağıdaki örnek, bir normal MFC'ye MFC DLL içinde tanımlanan bir API gösterir. Bu örnekte bildirimi içinde alınmış bir `extern "C" { }` C++ kullanıcılar için blok. Bu, çeşitli avantajları vardır. İlk olarak, DLL Apı'lerinizi kullanılabilir olmayan bir C++ istemci uygulamalar tarafından kolaylaştırır. İkinci olarak, C++ ad değiştirmeyi dışarı aktarılan adına uygulanmaz çünkü DLL yükünü azaltır. Son olarak, açıkça eklemek kolaylaştırır bir. DEF dosyası (sıralı olarak dışa aktarmak için) ad değiştirmeyi hakkında endişelenmenize gerek kalmadan.

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

API'sı tarafından kullanılan yapılara, MFC sınıflarından türetilmiş değil ve API üstbilgisinde tanımlanır. Bu DLL ve uygulama arasındaki arabirim karmaşıklığını azaltır ve DLL C programları tarafından kullanılabilir hale getirir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
