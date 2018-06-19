---
title: Derleyici ve bağlayıcı seçenekleri (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: ecfadce8-3a3f-40cc-bb01-b4731f8d2fcb
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e43418555722090c325c85bd4e77204640791b32
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33088486"
---
# <a name="compiler-and-linker-options-ccx"></a>Derleyici ve bağlayıcı seçenekleri (C + +/ CX)
Bir ortam değişkeni, C + +/ CX derleyici seçenekleri ve bağlayıcı seçenekleri için Windows çalışma zamanı uygulamaları oluşturulmasını destekler.  
  
## <a name="library-path"></a>Kitaplık yolu  
 % LIBPATH % ortam değişkeni .winmd dosyalarını aramak için varsayılan yolu belirtir.  
  
## <a name="compiler-options"></a>Derleyici seçenekleri  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|[/ZW](../build/reference/zw-windows-runtime-compilation.md)<br /><br /> /ZW:nostdlib|Windows çalışma zamanı dil uzantıları sağlar.<br /><br /> `nostdlib` Parametresi, derleme ve .winmd dosyalarını bulmak için standart, önceden tanımlanmış arama yolu kullanarak derleyici önler.<br /><br /> **/ZW** derleyici seçeneği örtük olarak aşağıdaki derleyici seçenekleri belirtir:<br /><br /> -   **/FI** derleyici tarafından gereken birçok türünü tanımlayan vccorlib.h üst bilgi dosyasını dahil edilmesi zorlar vccorlib.h.<br />-   [/FU](../build/reference/fu-name-forced-hash-using-file.md) işletim sistemi tarafından sağlanan ve Windows çalışma zamanı'nda birçok türünü tanımlayan Windows.winmd meta veri dosyası dahil edilmesi zorlar Windows.winmd.<br />-   **/FU** derleyici tarafından sağlanan ve ad alanları Platform ailesinde çoğu türlerini tanımlayan Platform.winmd meta veri dosyası dahil edilmesi zorlar Platform.winmd.|  
|[/AI](../build/reference/ai-specify-metadata-directories.md) *dir*|Tarafından belirtilen bir dizin ekler *dir* derleyici derleme ve .winmd dosyaları bulmak için kullandığı arama yolu için parametre.|  
|**/FU***dosyası*|Belirtilen modül veya .winmd dosyası ekleme zorlar. Diğer bir deyişle, belirtmeniz gerekmez `#using` *dosya* kaynak kodunuzdaki. Derleyici otomatik olarak eklenmesi, kendi Windows meta veri dosyası Platform.winmd zorlar.|  
|/D "WINAPI_FAMILY=2"|Windows çalışma zamanı ile uyumlu olan Win32 SDK'sı kümesini kullanılmasına olanak veren bir tanımı oluşturur.|  
  
## <a name="linker-options"></a>Bağlayıcı seçenekleri  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|/ APPCONTAINER [: YOK]|Yürütülebilir dosya appcontaıner (yalnızca) runnable olarak işaretler.|  
|/ WINMD [: {HAYIR&AMP;#124;YALNIZCA}]|Bir .winmd dosyası ve ilişkili bir ikili dosyası yayar. Bu seçenek yayınlaması için bir .winmd için bağlayıcı için geçirilmelidir.<br /><br /> **Hayır**— .winmd dosya yayma değil, ancak bir ikili dosya yayma.<br /><br /> **YALNIZCA**— .winmd dosya yayar, ancak bir ikili dosya yayma değil.|  
|/ WINMDFILE:*dosya adı*|Varsayılan .winmd dosya adı yerine yaymak üzere .winmd dosyasının adı. Birden çok dosya adları komut satırında belirtilirse, Soyadı kullanılır.|  
|/ WINMDDELAYSIGN [: YOK]|Kısmen .winmd dosyasını imzalar ve ortak anahtar ikili yerleştirir.<br /><br /> **Hayır**—(Default) .winmd dosya oturum değil.<br /><br /> / /WINMDKEYFILE veya /WINMDKEYCONTAINER de belirtilmedikçe WINMDDELAYSIGN bir etkisi yoktur.|  
|/ WINMDKEYCONTAINER:*adı*|Derlemeyi imzalamak için anahtar kapsayıcısını belirtir. *Adı* parametre meta veri dosyasını imzalamak için kullanılan anahtar kapsayıcısı karşılık gelir.|  
|/ WINMDKEYFILE:*dosya adı*|Bir anahtar veya derlemeyi imzalamak için bir anahtar çifti belirtir. *Filename* parametre meta veri dosyasını imzalamak için kullanılan anahtarına karşılık gelir.|  
  
### <a name="remarks"></a>Açıklamalar  
 Kullandığınızda **/ZW**, derleyici, DLL sürüme C çalışma zamanı'nın (CRT) otomatik olarak bağlar. Statik kitaplık sürüme bağlama verilmez ve herhangi bir evrensel Windows platformu uygulamasında izin verilmiyor CRT işlevleri kullanımını derleme zamanı hata neden olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapı uygulamalar ve kitaplıklar](../cppcx/building-apps-and-libraries-c-cx.md)