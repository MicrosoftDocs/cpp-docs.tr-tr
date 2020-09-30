---
title: Windows Masaüstü Sihirbazı
ms.date: 03/29/2019
f1_keywords:
- vc.appwiz.win32.overview
- vc.appwiz.win32.appset
helpviewer_keywords:
- Windows Desktop Wizard
- Win32 Project Wizard
ms.assetid: 5d7b3a5e-8461-479a-969a-67b7883725b9
ms.openlocfilehash: 47984b4c4416bf129efb226381fe778659aa16ca
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503513"
---
# <a name="windows-desktop-wizard"></a>Windows Masaüstü Sihirbazı

Windows Masaüstü Sihirbazı, Visual Studio 2017 ve sonraki sürümlerinde Win32 uygulama Sihirbazı 'Nın yerini alır. Sihirbaz, dört tür C++ projesi oluşturmanıza olanak tanır (aşağıdaki tabloda bulunan başlığında listelenmiştir). Her durumda, açtığınız proje türü için uygun olan ek seçenekleri belirtebilirsiniz.

   ![Windows Masaüstü Sihirbazı](media/windows-desktop-wizard.png)

Aşağıdaki tabloda her uygulama türü için hangi seçeneklerin kullanılabildiği gösterilmektedir.

|Destek türü|Konsol uygulaması|Yürütülebilir (Windows) uygulaması|Dinamik bağlantı kitaplığı|Statik kitaplık|
|---------------------|-------------------------|----------------------------------------|---------------------------|--------------------|
|**Boş proje**|Yes|Yes|Yes|Hayır|
|**Sembolleri dışarı aktar**|Hayır|Hayır|Yes|Hayır|
|**Ön derlenmiş üstbilgi**|Hayır|Hayır|Hayır|Yes|
|**ATL desteği**|Yes|Hayır|Hayır|Hayır|
|**MFC desteği**|Yes|Hayır|Hayır|Yes|

## <a name="overview"></a>Genel Bakış

Bu sihirbaz sayfası oluşturmakta olduğunuz Win32 uygulaması için geçerli proje ayarlarını açıklar. Varsayılan olarak, aşağıdaki seçenekler ayarlanır:

- Proje bir Windows uygulamasıdır.

- Proje boş değil.

- Proje dışa aktarma sembolleri içermiyor.

- Proje önceden derlenmiş bir üstbilgi dosyası kullanmıyor (Bu seçenek yalnızca statik kitaplık projeleri için kullanılabilir).

- Proje ne MFC ne de ATL için destek içerir.

## <a name="application-type"></a>Uygulama türü

Belirtilen uygulama türünü oluşturur.

|Seçenek|Açıklama|
|------------|-----------------|
|**Konsol uygulaması**|Bir konsol uygulaması oluşturur. Visual C++ [çalışma zamanı kitaplıkları](../c-runtime-library/c-run-time-library-reference.md) Ayrıca, ve gibi standart g/ç işlevleriyle konsol pencerelerinin çıkış ve giriş işlevlerini de sağlar `printf_s()` `scanf_s()` . Konsol uygulaması grafik kullanıcı arabirimine sahip değildir. Bir. exe dosyası olarak derlenir ve komut satırından tek başına bir uygulama olarak çalıştırılabilir.<br /><br /> Konsol uygulamasına MFC ve ATL desteği ekleyebilirsiniz.|
|**Windows uygulaması**|Win32 programı oluşturur. Win32 programı, grafik kullanıcı arabirimi oluşturmak için Win32 API çağrıları kullanılarak C veya C++ dilinde yazılmış bir yürütülebilir uygulamadır (EXE).<br /><br /> Windows uygulamasına MFC veya ATL desteği ekleyemezsiniz.|
|**Dinamik bağlantı kitaplığı**|Win32 dinamik bağlantı kitaplığı (DLL) oluşturur. Win32 DLL, MFC sınıfları yerine Win32 API çağrıları kullanan ve birden çok uygulama tarafından aynı anda kullanılabilen bir işlev kitaplığı görevi gören C veya C++ dilinde yazılmış bir ikili dosyadır.<br /><br /> Bu sihirbaz kullanılarak oluşturulan bir DLL uygulamasına MFC veya ATL desteği ekleyemezsiniz, ancak MFC **dll > yeni > proje**' yi seçerek BIR MFC DLL oluşturabilirsiniz.|
|**Statik kitaplık**|Statik bir kitaplık oluşturur. Statik kitaplık, çalıştırılabilir dosya oluşturulduğunda programınıza bağlanan nesneler ve bunların işlevlerini ve verilerini içeren bir dosyadır. Bu konu, bir statik kitaplık için başlangıç dosyalarının ve [proje özelliklerinin](../build/reference/property-pages-visual-cpp.md) nasıl oluşturulacağını açıklamaktadır. Statik kitaplık dosyası aşağıdaki avantajları sağlar:<br /><br />-Bir Win32 statik kitaplığı, üzerinde çalıştığınız uygulama MFC sınıfları yerine Win32 API çağrılar yaptığında yararlıdır.<br />-Bağlama işlemi, Windows uygulamanızın geri kalanının C 'de mi yoksa C++ dilinde mi yazıldığını belirtir.<br />-Statik bir kitaplığı, MFC tabanlı bir programa veya MFC olmayan bir programa bağlayabilirsiniz.|

## <a name="additional-options"></a>Ek seçenekler

Türüne bağlı olarak uygulama için destek ve seçenekleri tanımlar.

|Seçenek|Açıklama|
|------------|-----------------|
|**Boş proje**|Proje dosyalarının boş olduğunu belirtir. Kaynak kodu dosyaları (. cpp dosyaları, üst bilgi dosyaları, simgeler, araç çubukları, iletişim kutuları vb.) kümesine sahipseniz ve Visual C++ geliştirme ortamında bir proje oluşturmak istiyorsanız, önce boş bir proje oluşturmanız ve ardından dosyaları projeye eklemeniz gerekir.<br /><br /> Bu seçim statik kitaplık projeleri için kullanılamaz.|
|**Sembolleri dışarı aktar**|DLL projesinin sembolleri dışarı aktaracağını belirtir.|
|**Ön derlenmiş üstbilgi**|Statik kitaplık projesinin önceden derlenmiş üst bilgi kullandığını belirtir.|
|**Güvenlik geliştirme yaşam döngüsü (SDL) denetimleri**|SDL hakkında daha fazla bilgi için bkz. [Microsoft Security Development lifecycle (SDL) Işlem Kılavuzu](../build/reference/sdl-enable-additional-security-checks.md)|

## <a name="add-common-headers-for"></a>İçin ortak üst bilgiler ekle:

Visual C++ sağlanan kitaplıklarınızdan biri için destek ekleyin.

|Seçenek|Açıklama|
|------------|-----------------|
|**ATL**|Etkin Şablon kitaplığı 'ndaki (ATL) sınıflar için proje desteği içinde oluşturur. Yalnızca Win32 konsol uygulamaları için.<br /><br /> **Göz önünde** Bu seçenek, ATL kod sihirbazları kullanılarak ATL nesneleri ekleme desteğini göstermez. ATL nesnelerini yalnızca atl desteği olan ATL projelerine veya MFC projelerine ekleyebilirsiniz.|
|**MFC**|, Microsoft Foundation Class (MFC) kitaplığı için proje desteği ' nde oluşturulur. Yalnızca Win32 konsol uygulamaları ve statik kitaplıklar için.|

## <a name="remarks"></a>Açıklamalar

Bir Windows masaüstü uygulaması oluşturduktan sonra [genel](../ide/adding-a-generic-cpp-class.md#generic-c-class-wizard) kod Sihirbazı 'nı kullanarak genel C++ sınıfları ekleyebilirsiniz. HTML dosyaları, üst bilgi dosyaları, kaynaklar veya metin dosyaları gibi diğer öğeleri ekleyebilirsiniz.

> [!NOTE]
> ATL sınıfları ekleyemez ve yalnızca MFC 'yi destekleyen Windows Masaüstü uygulama türlerine MFC sınıfları ekleyebilirsiniz (önceki tabloya bakın).

Projeniz için sihirbaz tarafından oluşturulan dosyaları **Çözüm Gezgini**görüntüleyebilirsiniz. Sihirbazın projeniz için oluşturduğu dosyalar hakkında daha fazla bilgi için, proje tarafından oluşturulan dosya, bkz `ReadMe.txt` .. Dosya türleri hakkında daha fazla bilgi için, [Visual Studio C++ projeleri Için oluşturulan dosya türleri](../build/reference/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C++ proje türleri](../build/reference/visual-cpp-project-types.md)
