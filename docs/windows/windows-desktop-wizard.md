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
ms.openlocfilehash: 52ffd992480df517f8677e14161b697eb3ecc321
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787684"
---
# <a name="windows-desktop-wizard"></a>Windows Masaüstü Sihirbazı

Windows Masaüstü Sihirbazı'nı Visual Studio 2017 ve sonraki sürümlerinde Win32 Uygulama Sihirbazı değiştirir. Sihirbaz, C++ projeleri (aşağıdaki tablonun başlığında listelenen) dört türlerinden herhangi birini oluşturmanıza olanak sağlar. Her durumda, açtığınız proje türü için uygun olan diğer seçenekler belirtebilirsiniz. 

   ![Windows Masaüstü Sihirbazı](media/windows-desktop-wizard.png)

Aşağıdaki tablo, her uygulama türü için kullanılabilir olan seçenekleri belirtir.

|Destek türü|Konsol uygulaması|Yürütülebilir (Windows) uygulama|Dinamik bağlantı kitaplığı|Statik kitaplık|
|---------------------|-------------------------|----------------------------------------|---------------------------|--------------------|
|**Boş proje**|Evet|Evet|Evet|Hayır|
|**Sembolleri dışa aktarma**|Hayır|Hayır|Evet|Hayır|
|**Önceden derlenmiş üst bilgi**|Hayır|Hayır|Hayır|Evet|
|**ATL desteği**|Evet|Hayır|Hayır|Hayır|
|**MFC desteği**|Evet|Hayır|Hayır|Evet|

## <a name="overview"></a>Genel Bakış

Bu sihirbaz sayfası oluşturduğunuz Win32 uygulaması için geçerli proje ayarlarını açıklar. Varsayılan olarak, aşağıdaki seçenekleri ayarlıdır:

- Proje bir Windows uygulamasıdır.

- Proje boş değil.

- Proje dışa aktarma simgesi içerir.

- Proje (Bu seçenek yalnızca statik kitaplık projeleri için kullanılabilir) önceden derlenmiş üstbilgi dosyası kullanmaz.

- Proje MFC veya ATL için destek içerir.

## <a name="application-type"></a>Uygulama türü

Belirtilen uygulama türünü oluşturur.

|Seçenek|Açıklama|
|------------|-----------------|
|**Konsol uygulaması**|Bir konsol uygulaması oluşturur. Konsol programları ile geliştirilen [Konsolu işlevleri](https://msdn.microsoft.com/library/ms813137.aspx), konsolu windows karakter modu desteği sağlar. Visual C++ [çalışma zamanı kitaplıkları](../c-runtime-library/c-run-time-library-reference.md) ayrıca çıktısını sağlayın ve standart g/ç işlevleri ile Windows konsolu gibi giriş `printf_s()` ve `scanf_s()`. Bir konsol uygulaması grafik kullanıcı arabirimi var. Bir .exe dosyasının içine derleyen ve komut satırından bağımsız bir uygulama olarak çalıştırılabilir.<br /><br /> MFC ve ATL bir konsol uygulaması için destek ekleyebilirsiniz.|
|**Windows uygulama**|Bir Win32 programına oluşturur. Bir Win32 programına C veya C++, bir grafik kullanıcı arabirimi oluşturmak için Win32 API çağrıları kullanarak yazılmış bir yürütülebilir (EXE) uygulamasıdır.<br /><br /> MFC eklenemiyor veya bir Windows uygulaması için ATL desteği.|
|**Dinamik bağlantı kitaplığı**|Bir Win32 dinamik bağlantı kitaplığı (DLL) oluşturur. Bir Win32 DLL C veya C++, MFC sınıfları yerine Win32 API çağrılarını kullanır ve, paylaşılan bir kitaplık aynı anda birden çok uygulama tarafından kullanılabilecek işlevleri gibi davranır, ikili bir dosyadır.<br /><br /> Bu sihirbazı kullanılarak oluşturulan bir DLL uygulaması için MFC veya ATL desteği ekleme yapamazsınız, ancak bir MFC DLL oluşturabilirsiniz seçme ölçütü **yeni > Proje > MFC DLL**.|
|**Statik kitaplık**|Statik kitaplık oluşturur. Statik kitaplık nesneleri ve işlevleri ve yürütülebilir dosya oluşturulduğunda, programınız bağlanan veri içeren bir dosyadır. Bu konu başlangıç dosyalarının nasıl oluşturulacağını açıklar ve [proje özellikleri](../build/reference/property-pages-visual-cpp.md) statik kitaplığı. Statik kitaplık dosyası aşağıdaki avantajları sağlar:<br /><br />-Bir Win32 statik kitaplık, üzerinde çalıştığınız uygulama Win32 API yerine MFC sınıfları çağrılar yaparsa yararlıdır.<br />-Windows uygulamanızı geri kalanını c veya C++ yazılmış bağlama işlemi aynıdır.<br />MFC tabanlı bir program veya MFC olmayan programı-statik kitaplık bağlayabilirsiniz.|

## <a name="additional-options"></a>Ek Seçenekler

Destek ve kendi türüne bağlı olarak bir uygulama için seçenekleri tanımlar.

|Seçenek|Açıklama|
|------------|-----------------|
|**Boş proje**|Proje dosyalarını boş olduğunu belirtir. Kaynak kodu dosyaları (örneğin, .cpp dosyaları, üstbilgi dosyaları, simgeler, araç çubukları, iletişim kutuları ve benzeri) kümesine sahiptir ve bir proje Visual C++ geliştirme ortamında oluşturmak istiyorsanız, önce boş bir proje oluşturun, ardından gerekir dosyalar projeye ekleyin.<br /><br /> Bu seçim, statik kitaplık projeleri için kullanılamıyor.|
|**Sembolleri dışa aktarma**|DLL projesi sembolleri dışarı aktarır belirtir.|
|**Önceden derlenmiş üst bilgi**|Statik kitaplık proje önceden derlenmiş üst bilgi kullandığını belirtir.|
|**Güvenlik geliştirme yaşam döngüsü (SDL) denetimleri**|SDL hakkında daha fazla bilgi için bkz: [Microsoft Security Development Lifecycle (SDL) işlem kılavuzu](../build/reference/sdl-enable-additional-security-checks.md)|

## <a name="add-common-headers-for"></a>İçin ortak üst bilgileri ekleyin:

Visual C++'da sağlanan kitaplıkları biri için destek eklendi.

|Seçenek|Açıklama|
|------------|-----------------|
|**ATL**|Etkin Şablon kitaplığı (ATL) içinde sınıflar için proje desteği içine derler. Win32 konsol uygulamaları için yalnızca.<br /><br /> **Not** bu seçeneği, kod sihirbazları kullanarak ATL ATL nesneleri ekleme desteği göstermez. Yalnızca ATL projeler için ATL nesneler ekleyebilir veya ATL ile MFC projeleri destekler.|
|**MFC**|Microsoft Foundation Class (MFC) kitaplığı için proje desteği içine derler. Win32 konsol uygulamaları ve yalnızca statik kitaplıklar için.|

## <a name="remarks"></a>Açıklamalar

Windows masaüstü uygulaması oluşturduğunuzca genel C++ sınıflarını kullanarak ekleyebilirsiniz [genel](../ide/generic-cpp-class-wizard.md) kod Sihirbazı. HTML dosyaları, üstbilgi dosyaları, kaynaklar veya metin dosyaları gibi diğer öğeler ekleyebilirsiniz.

> [!NOTE]
> ATL sınıfları ekleyemezsiniz ve MFC desteği yalnızca bu Windows Masaüstü uygulama türleri için MFC sınıfları ekleyebilirsiniz (önceki tabloya bakın).

Projeniz için sihirbazın oluşturduğu dosyaları görüntüleyebilirsiniz **Çözüm Gezgini**. Projeniz için sihirbazın oluşturduğu dosyaları hakkında daha fazla bilgi için bkz: Proje tarafından oluşturulan dosya `ReadMe.txt`. Dosya türleri hakkında daha fazla bilgi için [Visual C++ projeleri için oluşturulan dosya türleri](../build/reference/file-types-created-for-visual-cpp-projects.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ Proje Türleri](../build/reference/visual-cpp-project-types.md)