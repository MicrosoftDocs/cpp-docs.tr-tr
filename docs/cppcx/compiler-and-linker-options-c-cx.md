---
description: 'Daha fazla bilgi edinin: derleyici ve bağlayıcı seçenekleri (C++/CX)'
title: Derleyici ve Bağlayıcı Seçenekleri (C++/CX)
ms.date: 01/22/2017
ms.assetid: ecfadce8-3a3f-40cc-bb01-b4731f8d2fcb
ms.openlocfilehash: 66f3cf5a08d7ca0a07b5708495f76902c2286436
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340430"
---
# <a name="compiler-and-linker-options-ccx"></a>Derleyici ve Bağlayıcı Seçenekleri (C++/CX)

Bir ortam değişkeni, C++/CX derleyici seçenekleri ve bağlayıcı seçenekleri Windows Çalışma Zamanı uygulamaların oluşturulmasını destekler.

## <a name="library-path"></a>Kitaplık yolu

% LIBPATH% ortam değişkeni,. winmd dosyalarını aramak için varsayılan yolu belirtir.

## <a name="compiler-options"></a>Derleyici seçenekleri

|Seçenek|Açıklama|
|------------|-----------------|
|[/ZW](../build/reference/zw-windows-runtime-compilation.md)<br /><br /> /ZW: nostdlib|Windows Çalışma Zamanı dil uzantılarını sunar.<br /><br /> `nostdlib`Parametresi derleyicinin derlemeyi ve. winmd dosyalarını bulmak için standart, önceden tanımlanmış arama yolunu kullanmasını önler.<br /><br /> **/ZW** derleyici seçeneği, aşağıdaki derleyici seçeneklerini örtülü olarak belirler:<br /><br />- **/FI** vccorlib. h, derleyicinin gerektirdiği birçok türü tanımlayan vccorlib. h üst bilgi dosyasının eklenmesine zorlar.<br />- [/Fu](../build/reference/fu-name-forced-hash-using-file.md) Windows. winmd, işletim sistemi tarafından sunulan Windows. winmd meta veri dosyasını eklemeyi zorlar ve Windows Çalışma Zamanı birçok türü tanımlar.<br />- **/Fu** Platform. winmd, derleyici tarafından sunulan platform. winmd meta veri dosyasının eklenmesini zorlar ve ad alanlarının platform ailesinden çoğu türü tanımlar.|
|[/AI](../build/reference/ai-specify-metadata-directories.md) *dizini*|*Dır* parametresi tarafından belirtilen bir dizin ekler ve derleyicinin derleme ve. winmd dosyalarını bulmak için kullandığı arama yoluna.|
|**/Fu**  *dosyası*|Belirtilen modülün veya. winmd dosyasının eklenmesine zorlar. Diğer bir deyişle, `#using` kaynak kodunuzda *Dosya* belirtmeniz gerekmez. Derleyici, kendi Windows meta veri dosyasının (platform. winmd) dahil edilmesini otomatik olarak zorlar.|
|/D "WINAPI_FAMILY = 2"|Windows Çalışma Zamanı ile uyumlu Win32 SDK alt kümesinin kullanımını sağlayan bir tanım oluşturur.|

## <a name="linker-options"></a>Bağlayıcı seçenekleri

|Seçenek|Açıklama|
|------------|-----------------|
|/APPCONTAINER [: NO]|Yürütülebilir dosyayı AppContainer 'da çalıştırılabilir olarak işaretler (yalnızca).|
|/WINMD [: {YALNıZCA&#124;}}]|Bir. winmd dosyası ve ilişkili bir ikili dosya yayar. Bu seçenek, bir. winmd 'nin yayınlanmalıdır bağlayıcıya geçirilmesi gerekir.<br /><br /> **Hayır**— bir. winmd dosyası oluşturmaz, ancak bir ikili dosya yayar.<br /><br /> **Yalnızca**— bir. winmd dosyası yayar, ancak bir ikili dosya oluşturmaz.|
|/WINMDFILE:*dosya adı*|Varsayılan. winmd dosya adı yerine, yayyapılacak. winmd dosyasının adı. Komut satırında birden çok dosya adı belirtilmişse, soyadı kullanılır.|
|/WINMDDELAYSIGN [: NO]|. Winmd dosyasını kısmen imzalar ve ortak anahtarı ikiliye koyar.<br /><br /> **Hayır**— (varsayılan). winmd dosyasını Imzalamamaz.<br /><br /> /WINMDKEYFILE veya/WINMDKEYCONTAINER da belirtilmedikçe/WINMDDELAYSIGN etkisizdir.|
|/WINMDKEYCONTAINER:*adı*|Bir derlemeyi imzalamak için bir anahtar kapsayıcısı belirtir. *Name* parametresi, meta veri dosyasını imzalamak için kullanılan anahtar kapsayıcısına karşılık gelir.|
|/WINMDKEYFILE:*dosya adı*|Derlemeyi imzalamak için bir anahtar veya anahtar çiftini belirtir. *Filename* parametresi, meta veri dosyasını imzalamak için kullanılan anahtara karşılık gelir.|

### <a name="remarks"></a>Açıklamalar

**/ZW** kullandığınızda, derleyici C çalışma ZAMANıNıN (CRT) dll sürümüne otomatik olarak bağlanır. Statik kitaplık sürümüne bağlanmasına izin verilmez ve bir Evrensel Windows Platformu uygulamasında izin verilmeyen CRT işlevlerinin kullanımı, derleme zamanı hatasına neden olur.

## <a name="see-also"></a>Ayrıca bkz.

[Uygulama ve kitaplık oluşturma](../cppcx/building-apps-and-libraries-c-cx.md)
