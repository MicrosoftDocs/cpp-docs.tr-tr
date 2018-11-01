---
title: Derleyici ve bağlayıcı seçenekleri (C + +/ CX)
ms.date: 01/22/2017
ms.assetid: ecfadce8-3a3f-40cc-bb01-b4731f8d2fcb
ms.openlocfilehash: 2165d802e6ff4bd530acac7c1ba6185c732a6499
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577298"
---
# <a name="compiler-and-linker-options-ccx"></a>Derleyici ve bağlayıcı seçenekleri (C + +/ CX)

Bir ortam değişkeni, C + +/ CX derleyici seçenekleri ve bağlayıcı seçenekleri için Windows çalışma zamanı uygulamaları oluşturmayı destekler.

## <a name="library-path"></a>Kitaplık yolu

% LIBPATH % ortam değişkeni .winmd dosyalarını aramak için varsayılan yolu belirtir.

## <a name="compiler-options"></a>Derleyici seçenekleri

|Seçenek|Açıklama|
|------------|-----------------|
|[/ZW](../build/reference/zw-windows-runtime-compilation.md)<br /><br /> /ZW:nostdlib|Windows çalışma zamanı dil uzantılarını etkinleştirir.<br /><br /> `nostdlib` Parametresi standart, önceden tanımlanmış bir arama yolu'ı kullanarak derleme ve .winmd dosyaları bulmak için derleyici engeller.<br /><br /> **/ZW** derleyici seçeneği, örtük olarak aşağıdaki derleyici seçeneklerinin belirtir:<br /><br />- **/FI** form veya vccorlib.h derleyici tarafından gereken birçok türü tanımlayan vccorlib.h üstbilgi dosyasının eklenmesi zorlar.<br />- [/FU](../build/reference/fu-name-forced-hash-using-file.md) Windows.winmd'i, hangi işletim sistemi tarafından sağlanır ve Windows çalışma zamanı'nda birçok türü tanımlayan Windows.winmd'i meta veri dosyası dahil edilmesi zorlar.<br />- **/FU** form veya Platform.winmd derleyici tarafından sağlanır ve ad alanları Platform ailede türlerdir tanımlayan Platform.winmd meta veri dosyası dahil edilmesi zorlar.|
|[/AI](../build/reference/ai-specify-metadata-directories.md) *dizini*|Tarafından belirtilen bir dizine ekler *dir* parametresi, derleyici derleme ve .winmd dosyaları bulmak için kullandığı arama yolu.|
|**/FU***dosyası*|Belirtilen modül veya .winmd dosyasının eklenmesi zorlar. Diğer bir deyişle, belirtmeniz gerekmez `#using` *dosya* , kaynak kodunuzdaki. Derleyici, otomatik olarak eklenmesi, kendi Windows meta veri dosyası Platform.winmd zorlar.|
|/D "WINAPI_FAMILY=2"|Bir alt kümesini Windows çalışma zamanı ile uyumlu olan Win32 SDK'sını kullanmayı sağlayan bir tanım oluşturur.|

## <a name="linker-options"></a>Bağlayıcı seçenekleri

|Seçenek|Açıklama|
|------------|-----------------|
|/ APPCONTAINER [: NO]|Çalıştırılabilir çalıştırılabilir (yalnızca) appcontainer içinde olarak işaretler.|
|/ WINMD [: {HAYIR&AMP;#124;YALNIZCA}]|Bir .winmd dosyası ve ilişkili bir ikili dosya yayar. Bu seçenek derleyicisindeki bir .winmd için bağlayıcı için geçirilmelidir.<br /><br /> **Hayır**— bir .winmd dosyası vermez, ancak bir ikili dosya gösterin.<br /><br /> **YALNIZCA**— bir .winmd dosyası yayar, ancak bir ikili dosya vermez.|
|/ WINMDFILE:*dosya adı*|Varsayılan .winmd dosyası adı yerine yaymak için .winmd dosyasının adı. Komut satırında birden çok dosya adı belirtilmişse Soyadı kullanılır.|
|/ WINMDDELAYSIGN DOSYASINI [: NO]|Kısmen .winmd dosyası imzalar ve ortak anahtar ikili yerleştirir.<br /><br /> **Hayır**—(Default) oturum .winmd dosyası değil.<br /><br /> / /WINMDKEYFILE veya /WINMDKEYCONTAINER de belirtilmezse wınmddelaysıgn dosyasını bir etkisi yoktur.|
|/ WINMDKEYCONTAINER:*adı*|Bir derlemeyi imzalamak için bir anahtar kapsayıcı belirtir. *Adı* parametresi metadata dosyasını imzalamak için kullanılan anahtar kapsayıcısı karşılık gelir.|
|/ WINMDKEYFILE:*dosya adı*|Bir anahtar veya derlemeyi imzalamak için bir anahtar çiftini belirtir. *Filename* parametresi metadata dosyasını imzalamak için kullanılan anahtarına karşılık gelir.|

### <a name="remarks"></a>Açıklamalar

Kullanırken **/ZW**, derleyici, DLL sürümü C çalışma zamanı'nın (CRT) otomatik olarak bağlar. Statik kitaplık sürümüne bağlama verilmez ve bir evrensel Windows platformu uygulaması içinde izin verilmiyor CRT işlevleri kullanımı bir derleme zamanı hatasına neden olur.

## <a name="see-also"></a>Ayrıca Bkz.

[Uygulamaları oluşturma ve kitaplıkları](../cppcx/building-apps-and-libraries-c-cx.md)