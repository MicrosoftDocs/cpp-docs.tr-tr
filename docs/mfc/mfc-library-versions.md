---
title: MFC Kitaplık Sürümleri
ms.date: 05/08/2019
helpviewer_keywords:
- class libraries [MFC], building versions
- version information [MFC], MFC library
- MFC class library
- MFC class library, building
- MFC libraries
- MFC, library versions
- libraries [MFC], versions
ms.openlocfilehash: b8e32366d9ff43bd6e5770f64f0ba9d8bf6e56ab
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856806"
---
# <a name="mfc-library-versions"></a>MFC Kitaplık Sürümleri

MFC kitaplığı, ANSI tek baytlı ve çok baytlı karakter kümesi (MBCS) kodunun yanı sıra Unicode (UTF-16LE, Windows-Native karakter kümesi olarak kodlanmış) sürümlerini destekleyen sürümlerde kullanılabilir. Her MFC sürümü bir statik kitaplık veya paylaşılan DLL olarak kullanılabilir. Ayrıca, büyüklüklere çok duyarlı olan ve bu denetimleri gerektirmeyen uygulamalar için, iletişim kutuları için MFC denetimlerini bırakan daha küçük bir MFC statik kitaplık sürümü de vardır. MFC kitaplıkları, x86, x64 ve ARM işlemcileri içeren desteklenen mimarilere yönelik hata ayıklama ve sürüm sürümlerinde kullanılabilir. MFC kitaplıklarının herhangi bir sürümüyle hem uygulamalar (. exe dosyaları) hem de dll 'Ler oluşturabilirsiniz. Ayrıca, yönetilen kodla arabirim oluşturma için derlenen MFC kitaplıkları kümesi de vardır. MFC paylaşılan DLL 'Leri kitaplık ikili uyumluluğunu göstermek için bir sürüm numarası içerir.

## <a name="automatic-linking-of-mfc-library-versions"></a>MFC kitaplık sürümlerinin otomatik bağlanması

MFC başlık dosyaları, derleme ortamınızda tanımlanan değerlere bağlı olarak, bağlanacak MFC kitaplığının doğru sürümünü otomatik olarak tespit ediyor. MFC üst bilgi dosyaları, MFC kitaplığının belirli bir sürümünde bağlantı sağlamak için bağlayıcıyı veren derleyici yönergeleri ekler.

Örneğin, AFX. H üstbilgi dosyası bağlayıcıya, MFC 'nin tam statik, sınırlı statik veya paylaşılan DLL sürümünde bağlantı oluşturmasını söyler; ANSI/MBCS veya Unicode sürümü; derleme yapılandırmanıza bağlı olarak, hata ayıklama veya perakende sürümü:

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

MFC başlık dosyaları ayrıca MFC kitaplıkları, Win32 kitaplıkları, OLE kitaplıkları, örneklerden oluşturulmuş OLE kitaplıkları, ODBC kitaplıkları vb. dahil olmak üzere tüm gerekli kitaplıkların bağlantı yönergelerini içerir.

## <a name="ansi-mbcs-and-unicode"></a>ANSI, MBCS ve Unicode

MFC ANSI/MBCS kitaplık sürümleri, ASCII gibi tek baytlı karakter kümelerini ve Shift-JıS gibi çok baytlı karakter kümelerini destekler. MFC Unicode Kitaplığı sürümleri, UTF-16LE geniş karakter kodlu biçimde Unicode 'U destekler. UTF-8 kodlamalı Unicode desteği için MFC 'nin ANSI/MBCS kitaplık sürümlerini kullanın.

Proje yapılandırmanızı IDE 'de tek baytlık, çok baytlı veya geniş karakter Unicode dize ve karakter desteğini kullanacak şekilde ayarlamak için, **Proje özellikleri** iletişim kutusunu kullanın. **Yapılandırma özellikleri** > **genel** sayfasında, **karakter kümesi** özelliğini tek baytlık bir karakter kümesi **kullanılacak şekilde ayarlanmamış şekilde ayarlayın** . Özelliği çok baytlı bir karakter kümesi kullanmak için **çok baytlı karakter kümesini** kullanacak şekilde veya Unicode **karakter kümesini** UTF-16 olarak kodlanmış Unicode kullanmak üzere kullanmak için ayarlayın.

MFC projeleri, UTF-16 geniş karakter Unicode desteğini göstermek için UNICODE \_ön işlemci sembolünü kullanır ve MBCS desteğini göstermek için MBCS \_. Bu seçenekler bir projede birbirini dışlıyor.

## <a name="mfc-static-library-naming-conventions"></a>MFC statik kitaplık adlandırma kuralları

MFC için statik kitaplıklar aşağıdaki adlandırma kurallarını kullanır. Kitaplık adları şu biçimdedir

> <em>u</em> AFX<em>CD 'si</em>. LıB

italik küçük harfle gösterilen harflerin, anlamları aşağıdaki tabloda gösterilen tanımlayıcıların yer tutucuları vardır:

|Belirleyici|Değerler ve anlamları|
|---------------|-------------------------|
|*larınız*|ANSI/MBCS (N) veya Unicode (U); iletişim kutularında MFC denetimleri olmayan sürüm için atla|
|*,*|İletişim kutularında MFC denetimleri olan sürüm (CW) veya olmadan (NMCD)|
|*TID*|Hata Ayıkla veya yayınla: D = Hata Ayıkla; Yayın için tanımlayıcı atla|

Aşağıdaki tabloda listelenen tüm kitaplıklar, desteklenen derleme mimarileri için \atlmfc\lib dizinine önceden oluşturulmuş olarak eklenmiştir.

|Kitaplık|Açıklama|
|-------------|-----------------|
|NAFXCW.LIB|MFC statik bağlantı kitaplığı, yayın sürümü|
|NAFXCWD.LIB|MFC statik bağlantı kitaplığı, hata ayıklama sürümü|
|UAFXCW.LIB|Unicode desteği olan MFC statik bağlantı kitaplığı, yayın sürümü|
|UAFXCWD.LIB|Unicode desteği olan MFC statik bağlantı kitaplığı, hata ayıklama sürümü|
|AFXNMCD.LIB|MFC iletişim kutusu denetimleri olmayan MFC statik bağlantı kitaplığı, yayın sürümü|
|AFXNMCDD.LIB|MFC iletişim kutusu denetimleri olmayan MFC statik bağlantı kitaplığı, hata ayıklama sürümü|

Statik kitaplıkların her biri için aynı temel adı ve bir. pdb uzantısına sahip hata ayıklayıcı dosyaları da mevcuttur.

## <a name="mfc-shared-dll-naming-conventions"></a>MFC paylaşılan DLL adlandırma kuralları

MFC paylaşılan DLL 'Leri de yapılandırılmış bir adlandırma kuralına uyar. Bu, hangi DLL veya kitaplığın hangi amaçla kullanılması gerektiğini bilmenizi kolaylaştırır.

MFC DLL 'Lerinde ikili uyumluluğu gösteren *Sürüm* numaraları vardır. Bir proje içinde uyumluluğu güvence altına almak için diğer kitaplıklarınız ve derleyici araç takımı ile aynı sürüme sahip MFC DLL 'Leri kullanın.

|DLL|Açıklama|
|---------|-----------------|
|MFC*sürümü*. DOSYASıNı|MFC DLL, ANSI veya MBCS yayın sürümü|
|MFC*Sürüm*U. dll|MFC DLL, Unicode yayın sürümü|
|MFC*Sürüm*D. dll|MFC DLL, ANSI veya MBCS hata ayıklama sürümü|
|MFC*Sürüm*ud 'si. DOSYASıNı|MFC DLL, Unicode hata ayıklama sürümü|
|MFCM*sürümü*. DOSYASıNı|Windows Forms denetimleri, ANSI veya MBCS yayın sürümü ile MFC DLL|
|MFCM*Sürüm*U. dll|Windows Forms denetimleri olan MFC DLL, Unicode yayın sürümü|
|MFCM*Sürüm*D. dll|Windows Forms denetimleri, ANSI veya MBCS hata ayıklama sürümü ile MFC DLL|
|MFCM*Sürüm*ud. DOSYASıNı|Windows Forms denetimleri olan MFC DLL, Unicode hata ayıklama sürümü|

Bu paylaşılan DLL 'Leri kullanan uygulamalar veya MFC uzantı dll 'Leri oluşturmak için gereken içeri aktarma kitaplıkları, DLL ile aynı temel ada sahip ancak. lib dosya adı uzantısına sahiptir. Paylaşılan DLL 'Leri kullandığınızda, küçük bir statik kitaplık hala kodunuzla bağlantılı olmalıdır; Bu kitaplık, MFCS*sürümü*{U} {D}. lib olarak adlandırılmıştır.

MFC 'nin paylaşılan DLL sürümüne dinamik olarak bağlanıyorsanız, bir uygulamadan veya bir MFC uzantısı DLL 'sinden olursa olsun, eşleşen MFC*sürümünü*dahil etmeniz gerekir. Ürününüzü dağıtırken DLL veya MFC*Sürüm*U. dll.

Uygulamalarınızla dağıtılabilecek Visual C++ dll 'lerin bir listesi için, bkz. [Microsoft Visual Studio 2017 için dağıtılabilir kod ve Microsoft Visual Studio 2017 SDK (yardımcı programları ve BuildServer dosyalarını Içerir)](/visualstudio/productinfo/2017-redistribution-vs) veya [Visual Studio 2019 için dağıtılabilir kod](/visualstudio/releases/2019/redistribution).

MFC 'de MBCS ve Unicode desteği hakkında daha fazla bilgi için bkz. [Unicode ve çok baytlı karakter kümesi (MBCS) desteği](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).

## <a name="dynamic-link-library-support"></a>Dinamik bağlantı kitaplık desteği

MFC ve MFC olmayan çalıştırılabilirler tarafından kullanılabilecek DLL 'Ler oluşturmak için statik veya paylaşılan dinamik MFC kitaplıklarını kullanabilirsiniz. Bunlar, yalnızca MFC uygulamaları ve MFC DLL 'Leri tarafından kullanılabilen MFC uzantı dll 'Lerinden ayırt edilebilmesi için "normal dll 'ler" veya "normal MFC DLL 'Leri" olarak adlandırılır. MFC statik kitaplıkları kullanılarak oluşturulan bir DLL, bazı durumlarda daha eski başvurularda USRDLL olarak adlandırılır, çünkü MFC DLL projeleri **\_USRDLL**Önişlemci sembolünü tanımlar. MFC paylaşılan DLL 'Leri kullanan bir DLL, bazı durumlarda eski başvurularda AFXDLL olarak adlandırılır, çünkü **\_AFXDLL**ön işlemci sembolünü tanımlar.

MFC statik kitaplıklarına bağlanarak DLL projenizi oluşturduğunuzda, DLL 'niz MFC paylaşılan DLL 'Leri olmadan dağıtılabilir. DLL projeniz içeri aktarma kitaplıkları MFC*sürümüne*bağlanır. LIB veya MFC*Sürüm*U. lib, eşleşen MFC PAYLAŞıLAN DLL MFC*sürümünü*dağıtmanız gerekir. Dll veya MFC*Sürüm*U. dll ile birlikte dll 'niz. Daha fazla bilgi için bkz. [DLL 'ler](../build/dlls-in-visual-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)
