---
description: "Daha fazla bilgi edinin: TN011: MFC 'yi DLL 'nin bir parçası olarak kullanma"
title: "TN011: Bir DLL'in bir Parçası Olarak MFC Kullanma"
ms.date: 11/04/2016
helpviewer_keywords:
- _USRDLL symbol
- USRDLLs, compiler switches
- TN011
- DLLs [MFC], linking
- MFC DLLs [MFC], linking regular MFC DLLs to MFC
ms.assetid: 76753e9c-59dc-40f6-b6a7-f6bb9a7c4190
ms.openlocfilehash: 11b50ce361fc9e41c48931daa6bffd30a8c9673e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216034"
---
# <a name="tn011-using-mfc-as-part-of-a-dll"></a>TN011: Bir DLL'in bir Parçası Olarak MFC Kullanma

Bu notta, MFC kitaplığını Windows dinamik bağlantı kitaplığının (DLL) bir parçası olarak kullanmanıza olanak tanıyan normal MFC DLL 'Leri açıklanmaktadır. Windows dll 'Leri bildiğiniz ve bunların nasıl oluşturulacağı varsayılmaktadır. MFC kitaplığı için Uzantılar oluşturabileceğiniz MFC uzantı dll 'Leri hakkında bilgi için bkz. [MFC 'Nin dll sürümü](../mfc/tn033-dll-version-of-mfc.md).

## <a name="dll-interfaces"></a>DLL arabirimleri

normal MFC DLL 'Leri, uygulama ile DLL arasındaki arabirimlerin C benzeri işlevlerde ya da açıkça verilmiş sınıflarda belirtilme olduğunu varsayar. MFC sınıf arabirimleri verilemiyor.

Hem DLL hem de bir uygulama MFC kullanmak istiyorsanız, MFC kitaplıklarının paylaşılan sürümünü kullanma ya da kitaplıkların bir kopyasına statik olarak bağlanma seçeneği vardır. Uygulama ve DLL her ikisi de MFC kitaplığının standart sürümlerinden birini kullanabilir.

normal MFC DLL 'Lerinin çeşitli avantajları vardır:

- DLL kullanan uygulamanın MFC kullanması gerekmez ve bir Visual C++ uygulaması olması gerekmez.

- MFC 'ye statik olarak bağlanan normal MFC DLL 'Lerinde, DLL boyutu yalnızca kullanılan ve bağlanan MFC ve C çalışma zamanı yordamlarına bağlıdır.

- MFC 'ye dinamik olarak bağlanan normal MFC DLL 'Leri sayesinde, MFC 'nin paylaşılan sürümünü kullanarak bellek tasarrufu önemli olabilir. Ancak, DLL 'niz ile paylaşılan DLL 'Leri, MFC \<*version*> . dll ve Msvvcrt. dll ' yi dağıtmanız gerekir \<*version*> .

- DLL tasarımı sınıfların nasıl uygulandıklarında bağımsızdır. DLL tasarımınız yalnızca istediğiniz API 'lere dışa aktarılabilir. Sonuç olarak, uygulama değişirse normal MFC DLL 'Leri hala geçerlidir.

- MFC 'ye statik olarak bağlanan normal MFC DLL 'Leriyle, hem DLL hem de uygulama MFC kullanıyorsa, uygulama ile DLL 'den farklı bir MFC sürümü isteyen bir sorun yoktur ve bunun tersi de geçerlidir. MFC kitaplığı her bir DLL veya EXE 'ye statik olarak bağlı olduğundan, hangi sürüme sahip olduğunuzdan ilgili bir soru yoktur.

## <a name="api-limitations"></a>API sınırlamaları

Bazı MFC işlevleri, teknik sınırlamalar veya bu hizmetler genellikle uygulama tarafından sağlandığı için DLL sürümü için geçerlidir. MFC 'nin geçerli sürümüyle, geçerli olmayan tek işlev `CWinApp::SetDialogBkColor` .

## <a name="building-your-dll"></a>DLL 'Nizi oluşturma

MFC 'ye statik olarak bağlanan normal MFC DLL 'Leri derlerken semboller `_USRDLL` ve `_WINDLL` tanımlanmalıdır. DLL kodunuz da aşağıdaki derleyici anahtarlarıyla derlenmelidir:

- **/D_WINDLL** derlemenin dll için olduğunu belirtir

- **/D_USRDLL** normal MFC DLL oluşturduğunuzu belirtir

Ayrıca, MFC 'ye dinamik olarak bağlanan normal MFC DLL 'Leri derlerken bu sembolleri tanımlamanız ve bu derleyici anahtarlarını kullanmanız gerekir. Ayrıca, sembol `_AFXDLL` tanımlanmalıdır ve DLL kodunuz ile derlenmesi gerekir:

- **/D_AFXDLL** MFC 'ye dinamik olarak bağlanan normal BIR MFC DLL oluşturduğunuzu belirtir

Uygulama ve DLL arasındaki arabirimlerin (API 'Ler) açıkça verilmesi gerekir. Arabirimlerinizi düşük bant genişliğine sahip olarak tanımlamanızı ve mümkünse yalnızca C arabirimlerini kullanmanızı öneririz. Doğrudan C arabirimlerinin daha karmaşık C++ sınıflarından korunması daha kolaydır.

API 'lerinizi hem C hem de C++ dosyalarına dahil edilebilir ayrı bir üstbilgiye yerleştirin. Örnek için, MFC gelişmiş kavramlar örnek [DLLScreenCap](../overview/visual-cpp-samples.md) başlığındaki ScreenCap. h başlığına bakın. İşlevlerinizi dışarı aktarmak için, bunları `EXPORTS` modül tanımı dosyanızın bölümüne girin (. DEF) veya `__declspec(dllexport)` işlev tanımlarınıza dahil edin. `__declspec(dllimport)`Bu işlevleri istemci yürütülebilir dosyasına aktarmak için kullanın.

MFC 'ye dinamik olarak bağlanan normal MFC DLL 'Lerinde, tüm aktarılmış işlevlerin başına AFX_MANAGE_STATE makrosunu eklemeniz gerekir. Bu makro geçerli modül durumunu DLL için bir tane olarak ayarlar. Bu makroyu kullanmak için, DLL 'den aktarılmış işlevlerin başlangıcına aşağıdaki kod satırını ekleyin:

`AFX_MANAGE_STATE(AfxGetStaticModuleState( ))`

## <a name="winmain---dllmain"></a>WinMain-> DllMain

MFC kitaplığı, `DllMain` [CWinApp](../mfc/reference/cwinapp-class.md) türetilmiş nesnelerinizi tipik bir MFC uygulamasında olarak başlatan standart Win32 giriş noktasını tanımlar. Tüm DLL 'ye özgü başlatmayı, bir normal MFC uygulamasında olduğu gibi [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) yöntemine yerleştirin.

Uygulama ana ileti göndericisinin sahibi olduğundan, [CWinApp:: Run](../mfc/reference/cwinapp-class.md#run) mekanizmasının dll 'ye uygulanmadığını unutmayın. DLL 'niz modsuz iletişimler görüntülüyorsa veya kendi ana çerçeve penceresine sahipse, uygulamanızın ana ileti göndericisi, [CWinApp::P reTranslateMessage](../mfc/reference/cwinapp-class.md#pretranslatemessage)' ı çağıran dll 'den aktarılmış bir yordamı çağırmalıdır.

Bu işlevin kullanımı için DLLScreenCap örneğine bakın.

`DllMain`MFC 'nin sağladığı işlev, DLL kaldırılmadan önce sınıfından türetilmiş olan, sınıfınızın [CWinApp:: ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) yöntemini çağırır `CWinApp` .

## <a name="linking-your-dll"></a>DLL 'Nizi bağlama

MFC 'ye statik olarak bağlanan normal MFC DLL 'Leri ile, DLL 'nizi Nafxcwd. lib veya NAFXCW. lib ile ve Libcmt. lib adlı C çalışma zamanlarının sürümüyle bağlamanız gerekir. Bu kitaplıklar önceden oluşturulmuştur ve Visual C++ kurulumu 'nu çalıştırdığınızda bu dosyalar belirtilerek yüklenebilir.

## <a name="sample-code"></a>Örnek Kod

Tüm örnek için MFC gelişmiş kavramları örnek program DLLScreenCap bölümüne bakın. Bu örnekte dikkat etmeniz gereken birkaç ilginç şey aşağıda verilmiştir:

- DLL 'nin ve uygulamanın derleyici bayrakları farklı.

- Bağlantı çizgileri ve. DLL ve uygulama için DEF dosyaları farklıdır.

- DLL 'yi kullanan uygulamanın C++ içinde olması gerekmez.

- Uygulama ile DLL arasındaki arabirim C veya C++ tarafından kullanılabilen bir API 'dir ve DLLScreenCap. def ile birlikte verilir.

Aşağıdaki örnek, MFC 'ye statik olarak bağlanan normal bir MFC DLL 'de tanımlanan bir API 'yi gösterir. Bu örnekte, bildirimi `extern "C" { }` C++ kullanıcıları için bir blokta alınmıştır. Bunun çeşitli avantajları vardır. İlk olarak, DLL API 'lerinizi C + + olmayan istemci uygulamaları tarafından kullanılabilir hale getirir. İkincisi, C++ ad değiştirmeyi, verilecek ada uygulanamadığı için DLL ek yükünü azaltır. Son olarak, ' a açıkça eklenmesini kolaylaştırır. DEF dosyası (sıraya göre dışarı aktarma için) değiştirmeyi adı hakkında endişelenmenize gerek kalmadan.

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

API tarafından kullanılan yapılar MFC sınıflarından türetilmez ve API üst bilgisinde tanımlanmıştır. Bu, DLL ile uygulama arasındaki arabirimin karmaşıklığını azaltır ve DLL 'yi C programları tarafından kullanılabilir hale getirir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
