---
title: MFC kitaplık sürümleri | Microsoft Docs
ms.custom: ''
ms.date: 1/09/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- class libraries [MFC], building versions
- version information [MFC], MFC library
- MFC class library
- MFC class library, building
- MFC libraries
- MFC, library versions
- libraries [MFC], versions
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9fb4f73d1a0360ddad3983179415d0f7fc2d3cda
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-library-versions"></a>MFC Kitaplık Sürümleri

MFC kitaplığını ANSI tek baytlı destekleyen sürümlerinde kullanılabilir ve Unicode (UTF-16LE, Windows yerel karakter kümesi kodlanmış) destekleyen sürümler yanı sıra (MBCS) kod birden çok baytlı karakter kümesi. Her MFC sürümü, bir statik kitaplık veya paylaşılan DLL olarak kullanılabilir. MFC denetimleri boyutuna çok önemli olan ve bu denetimleri gerekmeyen uygulamalar için iletişim kutuları için ayrıldığında daha küçük bir MFC statik kitaplık sürümü yok. MFC kitaplıkları hem hata ayıklama modunda kullanılabilir ve sürümleri x86, x64 ve ARM işlemcileri dahil desteklenen mimariler için serbest bırakın. Her iki uygulamayı (.exe dosyaları) oluşturabilir ve MFC kitaplıkları herhangi bir sürümüyle DLL'ler. Var olan arabirim, yönetilen kod için derlenmiş MFC kitaplıkları kümesi de. MFC DLL'leri paylaşılan kitaplığı ikili uyumluluğu belirtmek için bir sürüm numarasını içerir.

## <a name="automatic-linking-of-mfc-library-versions"></a>MFC kitaplık sürümleri otomatik bağlama

MFC başlık dosyaları yapı ortamınızda tanımlı değerlere göre doğru bağlamak için MFC kitaplık sürümünü otomatik olarak belirleyin. MFC başlık dosyaları, belirli bir MFC kitaplık sürümünü bağlamak için derleyici yönergeleri bağlayıcı bilgilendirerek ekleyin.

Örneğin, AFX. H üstbilgi dosyası tam statik, sınırlı statik veya paylaşılan MFC'nin DLL sürümü bağlamak için bağlayıcı söyler; ANSI/MBCS veya Unicode sürümü; ve yapı yapılandırmanıza bağlı olarak hata ayıklama veya perakende sürümü:

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

MFC başlık dosyaları MFC kitaplıkları, Win32 kitaplıkları, OLE kitaplıklarının, örneklerinden yerleşik OLE kitaplıklarının, ODBC kitaplıkları vb. dahil olmak üzere tüm gerekli kitaplıklarında bağlamak için yönergeleri de içerir. 

## <a name="ansi-mbcs-and-unicode"></a>ANSI, MBCS ve Unicode

Hem tek baytlı karakter kümeleri ASCII gibi MFC ANSI/MBCS kitaplık sürümleri destekler ve birden çok baytlı karakter Shift-JIS gibi ayarlar. MFC Unicode kitaplık sürümleri, UTF-16LE joker karakter kodlanmış biçimde Unicode'u destekler. Unicode desteği UTF-8 kodlanmış için MFC ANSI/MBCS kitaplığı sürümlerini kullanın.

Tek baytlı, birden çok baytlı ve geniş karakter Unicode dize ve karakter desteği IDE içinde kullanmak için proje yapılandırmanızı ayarlamak için kullanın **proje özelliklerini** iletişim. İçinde **yapılandırma özellikleri** > **genel** sayfasında **karakter kümesi** özelliğine **ayarlanmamış** kullanmak için bir tek baytlı karakter kümesi. Özellik kümesine **kullanmak çok baytlı karakter kümesi** birden çok baytlı karakter kümesi kullanmak için veya **Unicode karakter kümesini kullanmak** UTF-16 kodlanmış Unicode kullanılacak.

MFC projeleri kullanmak önişlemci sembolü  **\_UNICODE** UTF-16 joker karakter Unicode desteği göstermek için ve  **\_MBCS** MBCS Desteği belirtmek için. Bu seçenekler bir proje ile karşılıklı olarak birbirini dışlar.

## <a name="mfc-static-library-naming-conventions"></a>MFC statik kitaplık adlandırma kuralları

MFC için statik kitaplıklar aşağıdaki adlandırma kurallarını kullanın. Kitaplık adlarının biçimi şöyledir:

> *u*AFX*c**d*.LIB

Burada italik olarak gösterilen küçük harfler, anlamları aşağıdaki tabloda gösterilen tanımlayıcıları için yer tutucuları şunlardır:

|Belirleyici|Değerleri ve anlamları|
|---------------|-------------------------|
|*u*|ANSI/MBCS (N) ya da Unicode (U); MFC iletişim kutuları denetimlerinde olmadan sürümü için atlayın|
|*c*|MFC iletişim kutuları (FA) veya (NMCD) olmadan denetimleri sürümüyle|
|*d*|Hata ayıklama veya yayın: D Debug; = Yayın için belirleyici atlayın|

Aşağıdaki tabloda listelenen tüm kitaplıkları dahil desteklenen yapı mimarileri \atlmfc\lib dizininde önceden oluşturulmuş.

|Kitaplığı|Açıklama|
|-------------|-----------------|
|NAFXCW.LIB|MFC statik bağlantı kitaplığı, yayın sürümü|
|NAFXCWD.LIB|MFC statik bağlantı kitaplığı, hata ayıklama sürümü|
|UAFXCW.LIB|Unicode desteği, yayın sürümü ile MFC statik bağlantı kitaplığı|
|UAFXCWD.LIB|Unicode desteği, hata ayıklama sürümü ile MFC statik bağlantı kitaplığı|
|AFXNMCD.LIB|MFC iletişim kutusu denetimleri, yayın sürümü olmadan MFC statik bağlantı kitaplığı|
|AFXNMCDD.LIB|MFC iletişim kutusu denetimleri, hata ayıklama sürümü olmadan MFC statik bağlantı kitaplığı|

Aynı taban adına ve .pdb uzantısına sahip hata ayıklayıcı dosyaları de her statik kitaplıklar için kullanılabilir.

## <a name="mfc-shared-dll-naming-conventions"></a>MFC DLL adlandırma kuralları paylaşılan

MFC DLL'leri de izleme yapılandırılmış bir adlandırma kuralı paylaşılan. Bu, hangi DLL'i veya kitaplığı hangi amaçla kullanılmalı bilmeniz kolaylaştırır.

MFC DLL'leri sahip *sürüm* ikili uyumluluğu gösteren sayı. Diğer kitaplıkları ve bir projede uyumluluğu güvence altına almak için derleyici araç setini aynı sürüme sahip MFC DLL'leri kullanın.

|DLL|Açıklama|
|---------|-----------------|
|MFC*sürüm*. DLL|MFC DLL, ANSI veya MBCS yayın sürümü|
|MFC*sürüm*U.DLL|MFC DLL, Unicode yayın sürümü|
|MFC*sürüm*D.DLL|MFC DLL, ANSI veya MBCS hata ayıklama sürümü|
|MFC*sürüm*UD. DLL|MFC DLL, Unicode hata ayıklama sürümü|
|MFCM*sürüm*. DLL|Windows Forms denetimleri ile MFC DLL ANSI veya MBCS yayın sürümü|
|MFCM*sürüm*U.DLL|Windows Forms denetimleri, Unicode yayın sürümü ile MFC DLL|
|MFCM*sürüm*D.DLL|Windows Forms denetimleri ile MFC DLL ANSI veya MBCS hata ayıklama sürümü|
|MFCM*sürüm*UD. DLL|Windows Forms denetimleri, Unicode hata ayıklama sürümü ile MFC DLL|

İçeri aktarma kitaplıkları uygulamalar veya MFC uzantı DLL'leri bu paylaşılan DLL'leri kullanan oluşturmak için gereken DLL olarak aynı taban adına sahip ancak .lib dosya adı uzantısına sahiptir. Paylaşılan dll kullandığınızda, küçük bir statik kitaplık ile kodunuzu hala bağlı gerekir; Bu kitaplık MFCS adlı*sürüm*{U} {D} .lib.

Bir uygulama veya MFC uzantı DLL'si olup paylaşılan MFC'nin DLL sürümü, için dinamik olarak bağlıyorsanız, eşleşen MFC içermelidir*sürüm*. DLL ya da MFC*sürüm*ürününüzü dağıttığınızda U.DLL.

Uygulamalarınızla dağıtılabilir Visual C++ DLL'leri listesi için bkz: [Microsoft Visual Studio 2017 ve Microsoft Visual Studio 2017 SDK (içerir yardımcı programları ve BuildServer Dosyaları) için dağıtılabilir kod](http://go.microsoft.com/fwlink/p/?LinkId=823098).

MFC MBCS ve Unicode desteği hakkında daha fazla bilgi için bkz: [Unicode ve çok baytlı karakter kümesi (MBCS) desteği](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).

## <a name="dynamic-link-library-support"></a>Dinamik bağlantı kitaplık desteği

MFC ve MFC dışı çalıştırılabilirler tarafından kullanılan DLL'leri oluşturmak için ya da statik veya paylaşılan dinamik MFC kitaplıkları kullanabilirsiniz. Bunlar "normal DLL'ler" veya "Normal MFC DLL'leri" olarak adlandırılır, bunları MFC uzantı DLL'leri yalnızca ayırt etmek için DLL'leri MFC uygulamaları ve MFC tarafından kullanılan. MFC DLL projeleri önişlemci sembolü tanımlamak için MFC statik kitaplıklar kullanılarak oluşturulmuş bir DLL bir USRDLL eski başvurularında adlandırılır  **\_USRDLL**. Önişlemci sembolü tanımladığından kullanan MFC DLL'leri paylaşılan DLL AFXDLL eski başvurular da adlandırılır  **\_AFXDLL**.

MFC statik kitaplıklar bağlayarak DLL projesi oluşturduğunuzda, DLL MFC DLL'leri paylaşılan olmadan dağıtılabilir. Ne zaman DLL projenizi bağlantıları içeri aktarma kitaplıkları MFC*sürüm*. LIB ya da MFC*sürüm*U.LIB, dağıtmanız gerekir eşleştirme MFC DLL MFC paylaşılan*sürüm*. DLL ya da MFC*sürüm*DLL birlikte U.DLL. Daha fazla bilgi için bkz: [DLL'leri](../build/dlls-in-visual-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

[Genel MFC Konuları](../mfc/general-mfc-topics.md)  
