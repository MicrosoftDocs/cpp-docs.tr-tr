---
title: MFC Kitaplık Sürümleri
ms.date: 1/09/2018
helpviewer_keywords:
- class libraries [MFC], building versions
- version information [MFC], MFC library
- MFC class library
- MFC class library, building
- MFC libraries
- MFC, library versions
- libraries [MFC], versions
ms.openlocfilehash: c0dc724566063066175ea54e2b7734892e3c6e05
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62238513"
---
# <a name="mfc-library-versions"></a>MFC Kitaplık Sürümleri

MFC Kitaplığı ANSI tek baytlık destekleyen sürümler halinde bulunmaktadır ve çok baytlı karakterin Unicode (UTF-16LE, Windows yerel karakter kümesi kodlanmış) destekleyen sürümler yanı sıra (MBCS) kodu ayarlayın. Her MFC sürüm, statik bir kitaplık veya paylaşılan DLL olarak kullanılabilir. MFC denetimleri boyutuna çok hassas olan ve bu denetimleri gerekmeyen uygulamalar için iletişim kutuları için ayrıldığında daha küçük bir MFC statik kitaplık sürümü de mevcuttur. MFC kitaplıkları, hem hata ayıklama kullanılabilir ve yayın sürümleri için x86 x64 ve ARM işlemcileri desteklenen mimariler. Her iki uygulama (.exe dosyaları) oluşturabilir ve DLL'ler ile MFC kitaplıklarını herhangi bir sürümü. Var olan yönetilen kod ile arabirim için derlenmiş MFC kitaplıkları da bir dizi. MFC DLL'leri paylaşılan kitaplığı ikili uyumluluğu belirtmek için bir sürüm numarası içerir.

## <a name="automatic-linking-of-mfc-library-versions"></a>MFC kitaplık sürümleri otomatik bağlama

MFC üstbilgi dosyalarındaki derleme ortamınızda tanımlanmış değerleri temel alarak doğru bağlamak için MFC kitaplık sürümünü otomatik olarak belirler. MFC üstbilgi dosyalarındaki MFC Kitaplığı belirli bir sürümüne bağlamak için bağlayıcı söyleyen derleyici yönergeleri ekleyin.

Örneğin, AFX. H üstbilgi dosyası tam statik, sınırlı statik veya paylaşılan MFC'nin DLL sürümü bağlamak için bilgilendirir; ANSI/MBCS veya Unicode sürümü; ve yapı yapılandırmanıza bağlı olarak, perakende veya hata ayıklama sürümü:

```cpp
#ifndef _AFXDLL
    #ifdef _AFX_NO_MFC_CONTROLS_IN_DIALOGS
        #ifdef _DEBUG
            #pragma comment(lib, "afxnmcdd.lib")
        #else
            #pragma comment(lib, "afxnmcd.lib")
        #endif
        #pragma comment(linker, "/include:__afxNoMFCControlSupportInDialogs")
        #pragma comment(linker, "/include:__afxNoMFCControlContainerInDialogs")
    #endif
    #ifndef _UNICODE
        #ifdef _DEBUG
            #pragma comment(lib, "nafxcwd.lib")
        #else
            #pragma comment(lib, "nafxcw.lib")
        #endif
    #else
        #ifdef _DEBUG
            #pragma comment(lib, "uafxcwd.lib")
        #else
            #pragma comment(lib, "uafxcw.lib")
        #endif
    #endif
#else
    #ifndef _UNICODE
        #ifdef _DEBUG
            #pragma comment(lib, "mfc" _MFC_FILENAME_VER "d.lib")
            #pragma comment(lib, "mfcs" _MFC_FILENAME_VER "d.lib")
        #else
            #pragma comment(lib, "mfc" _MFC_FILENAME_VER ".lib")
            #pragma comment(lib, "mfcs" _MFC_FILENAME_VER ".lib")
        #endif
    #else
        #ifdef _DEBUG
            #pragma comment(lib, "mfc" _MFC_FILENAME_VER "ud.lib")
            #pragma comment(lib, "mfcs" _MFC_FILENAME_VER "ud.lib")
        #else
            #pragma comment(lib, "mfc" _MFC_FILENAME_VER "u.lib")
            #pragma comment(lib, "mfcs" _MFC_FILENAME_VER "u.lib")
        #endif
    #endif
#endif
```

MFC üstbilgi dosyalarındaki MFC kitaplıkları, Win32 kitaplıklarına, OLE kitaplıkları, örnekleri yerleşik OLE kitaplıkları, ODBC kitaplığı ve benzeri gibi tüm gerekli kitaplıklarında bağlamak için yönergeleri de içerir.

## <a name="ansi-mbcs-and-unicode"></a>ANSI MBCS ve Unicode

ANSI/MBCS MFC kitaplık sürümleri gibi ASCII hem tek baytlı karakter kümesi desteği ve çok baytlı karakter Shift-JIS gibi ayarlar. Unicode MFC kitaplık sürümleri, UTF-16LE geniş karakter kodlanmış biçimde Unicode'u destekler. UTF-8 kodlamalı Unicode desteği için ANSI/MBCS MFC kitaplık sürümleri kullanın.

IDE'de tek baytlık, çok baytlı veya geniş karakter Unicode dize ve karakter desteği kullanmak için proje yapılandırmasını ayarlamak için kullanın **proje özellikleri** iletişim. İçinde **yapılandırma özellikleri** > **genel** sayfasında **karakter kümesi** özelliğini **ayarlı değil** kullanmak için bir tek baytlı karakter kümesi. Özelliğini **kullanmak çok baytlı karakter kümesi** bir çok baytlı karakter kümesini kullandırır veya **Unicode karakter kümesi kullanan** Unicode UTF-16 olarak kodlanmış kullanılacak.

MFC projeleri kullanmak önişlemci sembolü \_UNICODE UTF-16 geniş karakter Unicode desteği, belirtmek ve \_MBCS belirtmek için MBCS desteği. Bu projede birbirini dışlayan seçeneklerdir.

## <a name="mfc-static-library-naming-conventions"></a>MFC statik kitaplık adlandırma kuralları

Statik kitaplıklar için MFC aşağıdaki adlandırma kurallarını kullanın. Kitaplık adlarının biçimi şöyledir:

> <em>u</em>AFX<em>cd</em>.LIB

italik olarak küçük gösterilen harf tanımlayıcıları, anlamları aşağıdaki tabloda gösterilen yer tutucular nerede:

|Belirleyici|Değerleri ve anlamları|
|---------------|-------------------------|
|*u*|ANSI/MBCS (N) veya Unicode (U); iletişim kutularındaki denetimler MFC olmadan sürümü için Atla|
|*c*|MFC denetim iletişim kutuları (CW) veya (NMCD) olmadan bir sürümle|
|*d*|Hata ayıklama veya sürüm: D; Debug = Yayın için belirticisini atlayan|

Aşağıdaki tabloda listelenen tüm kitaplıkları içerdiği için desteklenen derleme mimarileri \atlmfc\lib dizininde önceden oluşturulmuş.

|Kitaplığı|Açıklama|
|-------------|-----------------|
|NAFXCW.LIB|MFC statik bağlantı kitaplığı sürümü|
|NAFXCWD.LIB|MFC statik bağlantı kitaplığı, hata ayıklama sürümü|
|UAFXCW.LIB|Sürümü Unicode desteği olan MFC statik bağlantı kitaplığı|
|UAFXCWD.LIB|Unicode desteği, hata ayıklama sürümü ile MFC statik bağlantı kitaplığı|
|AFXNMCD.LIB|MFC iletişim kutusu denetimleri, yayın sürümünü olmadan MFC statik bağlantı kitaplığı|
|AFXNMCDD.LIB|MFC iletişim kutusu denetimleri, hata ayıklama sürümü olmayan MFC statik bağlantı kitaplığı|

Aynı temel ada ve bir .pdb uzantısına sahip hata ayıklayıcı dosyaları aynı zamanda her bir statik kitaplıklar için kullanılabilir.

## <a name="mfc-shared-dll-naming-conventions"></a>MFC paylaşılan DLL adlandırma kuralları

MFC DLL'leri izleme bir yapılandırılmış adlandırma kuralı da paylaşılan. Bu, hangi DLL veya kitaplık hangi bir amaç için kullanmaları bilmek kolaylaştırır.

MFC DLL'leri sahip *sürüm* ikili uyumluluğu gösteren sayı. MFC DLL'leri, diğer kitaplık ve derleyici araç takımı, proje içinde uyumluluğu güvence altına almak için aynı sürüme sahip kullanın.

|DLL|Açıklama|
|---------|-----------------|
|MFC*sürüm*. DLL|MFC DLL, ANSI veya MBCS yayın sürümü|
|MFC*sürüm*U.DLL|MFC DLL, Unicode sürümü|
|MFC*sürüm*D.DLL|MFC DLL, ANSI veya MBCS hata ayıklama sürümü|
|MFC*sürüm*UD. DLL|MFC DLL, Unicode hata ayıklama sürümü|
|MFCM*sürüm*. DLL|MFC DLL ile Windows Forms denetimleri, ANSI veya MBCS yayın sürümü|
|MFCM*sürüm*U.DLL|MFC DLL ile Windows Forms denetimleri, Unicode sürümü|
|MFCM*sürüm*D.DLL|MFC DLL ile Windows Forms denetimleri, ANSI veya MBCS hata ayıklama sürümü|
|MFCM*sürüm*UD. DLL|MFC DLL ile Windows Forms denetimleri, Unicode hata ayıklama sürümü|

İçeri aktarma kitaplıkları uygulamalar veya MFC uzantısı DLL'leri bu paylaşılan DLL kullanan oluşturmak için gereken DLL aynı temel ada sahip ancak bir .lib dosya adı uzantısına sahip. Paylaşılan dll kullandığınızda, küçük bir statik kitaplık hala kodunuzla bağlanması gerekir; Bu kitaplık MFCS adlı*sürüm*.lib {U} {D}.

Bir uygulama veya bir MFC uzantılı DLL olup olmadığını, MFC paylaşılan DLL sürümü dinamik olarak bağlıyorsanız, eşleşen MFC içermelidir*sürüm*. DLL veya MFC*sürüm*ürününüzü dağıttığınızda U.DLL.

Uygulamalarınızı yeniden dağıtılabilir Visual C++ DLL'lerini listesi için bkz. [Microsoft Visual Studio 2017 ve Microsoft Visual Studio 2017 SDK'sı (içerir yardımcı programları ve BuildServer Dosyaları) için dağıtılabilir kod](http://go.microsoft.com/fwlink/p/?LinkId=823098).

MFC MBCS ve Unicode desteği hakkında daha fazla bilgi için bkz. [Unicode ve çok baytlı karakter kümesi (MBCS) desteği](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).

## <a name="dynamic-link-library-support"></a>Dinamik bağlantı kitaplık desteği

Ya da statik veya paylaşılan dinamik MFC kitaplıkları, MFC ve MFC olmayan yürütülebilir dosyaları tarafından kullanılabilecek DLL'leri oluşturmak için kullanabilirsiniz. Bunlar "Normal DLL'leri" veya "Normal MFC DLL'leri" olarak adlandırılır, MFC uzantı yalnızca dll dosyaları bunları ayırt etmek için DLL'leri MFC uygulamaları ve MFC tarafından kullanılan. MFC DLL projelerinde önişlemci sembolü tanımlamak için bir DLL, MFC statik kitaplıklar kullanılarak oluşturulan bir USRDLL eski başvurularında adlandırılır  **\_USRDLL**. Önişlemci sembolü tanımladığından kullanan MFC DLL'leri paylaşılan DLL AFXDLL eski başvurularında adlandırılır  **\_AFXDLL**.

DLL'niz MFC statik kitaplıklara bağlantılandırarak, DLL projesi oluşturduğunuzda, MFC DLL'leri paylaşılan olmadan dağıtılabilir. İçeri aktarma kitaplıkları MFC DLL projenize bağlantı zaman*sürüm*. LIB ya da MFC*sürüm*U.LIB, dağıtmanız gerekir eşleşen MFC paylaşılan MFC DLL*sürüm*. DLL veya MFC*sürüm*U.DLL DLL'niz ile birlikte. Daha fazla bilgi için [DLL'leri](../build/dlls-in-visual-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)
