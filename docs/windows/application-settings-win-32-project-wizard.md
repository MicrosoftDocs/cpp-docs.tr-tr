---
title: Uygulama ayarları, Win 32 Proje Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.appwiz.win32.appset
dev_langs:
- C++
helpviewer_keywords:
- application settings [C++]
- Win32 Project Wizard, application settings
ms.assetid: d6b818f0-9b23-4793-a6c5-df1c8c594bad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 948b720df6094ddd4124bb496cabb3c83a3cacf0
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652994"
---
# <a name="application-settings-win-32-project-wizard"></a>Uygulama Ayarları, Win 32 Proje Sihirbazı
Win32 Proje seçeneklerini ayarlamak için sihirbazın bu sayfayı kullanın.  
  
## <a name="application-type"></a>Uygulama türü  
 Belirtilen uygulama türünü oluşturur.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Konsol uygulaması**|Bir konsol uygulaması oluşturur. Konsol programları ile geliştirilen [Konsolu işlevleri](https://msdn.microsoft.com/library/ms813137.aspx), konsolu windows karakter modu desteği sağlar. Visual C++ [çalışma zamanı kitaplıkları](../c-runtime-library/c-run-time-library-reference.md) ayrıca çıktısını sağlayın ve standart g/ç işlevleri ile Windows konsolu gibi giriş `printf_s()` ve `scanf_s()`. Bir konsol uygulaması grafik kullanıcı arabirimi var. Bir .exe dosyasının içine derleyen ve komut satırından bağımsız bir uygulama olarak çalıştırılabilir.<br /><br /> MFC ve ATL bir konsol uygulaması için destek ekleyebilirsiniz.|  
|**Windows uygulama**|Bir Win32 programına oluşturur. Bir Win32 programına C veya C++, bir grafik kullanıcı arabirimi oluşturmak için Win32 API çağrıları kullanarak yazılmış bir yürütülebilir (EXE) uygulamasıdır.<br /><br /> MFC eklenemiyor veya bir Windows uygulaması için ATL desteği.|  
|**DLL**|Bir Win32 dinamik bağlantı kitaplığı (DLL) oluşturur. Bir Win32 DLL C veya C++, MFC sınıfları yerine Win32 API çağrılarını kullanır ve, paylaşılan bir kitaplık aynı anda birden çok uygulama tarafından kullanılabilecek işlevleri gibi davranır, ikili bir dosyadır.<br /><br /> MFC eklenemiyor veya bir DLL uygulaması için ATL desteği. DLL sembolleri dışa aktarır belirtebilirsiniz.|  
|**Statik kitaplık**|Statik kitaplık oluşturur. Statik kitaplık nesneleri ve işlevleri ve yürütülebilir dosya oluşturulduğunda, programınız bağlanan veri içeren bir dosyadır. Bu konu başlangıç dosyalarının nasıl oluşturulacağını açıklar ve [proje özellikleri](../ide/property-pages-visual-cpp.md) statik kitaplığı. Statik kitaplık dosyası aşağıdaki avantajları sağlar:<br /><br /> -Bir Win32 statik kitaplık, üzerinde çalıştığınız uygulama Win32 API yerine MFC sınıfları çağrılar yaparsa yararlıdır.<br />-Windows uygulamanızı geri kalanını c veya C++ yazılmış bağlama işlemi aynıdır.<br />MFC tabanlı bir program veya MFC olmayan programı-statik kitaplık bağlayabilirsiniz.|  
  
## <a name="additional-options"></a>Ek Seçenekler  
 Destek ve kendi türüne bağlı olarak bir uygulama için seçenekleri tanımlar.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Boş proje**|Proje dosyalarını boş olduğunu belirtir. Kaynak kodu dosyaları (örneğin, .cpp dosyaları, üstbilgi dosyaları, simgeler, araç çubukları, iletişim kutuları ve benzeri) kümesine sahiptir ve bir proje Visual C++ geliştirme ortamında oluşturmak istiyorsanız, önce boş bir proje oluşturun, ardından gerekir dosyalar projeye ekleyin.<br /><br /> Bu seçim, statik kitaplık projeleri için kullanılamıyor.|  
|**Sembolleri dışa aktarma**|DLL projesi sembolleri dışarı aktarır belirtir.|  
|**Önceden derlenmiş üst bilgi**|Statik kitaplık proje önceden derlenmiş üst bilgi kullandığını belirtir.|  
|Güvenlik geliştirme yaşam döngüsü (SDL) denetimleri|SDL hakkında daha fazla bilgi için bkz: [Microsoft Security Development Lifecycle (SDL) işlem kılavuzu](../build/reference/sdl-enable-additional-security-checks.md)|  
  
## <a name="add-support-for"></a>İçin destek eklendi  
 Visual C++'da sağlanan kitaplıkları biri için destek eklendi.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**ATL**|Etkin Şablon kitaplığı (ATL) içinde sınıflar için proje desteği içine derler. Win32 konsol uygulamaları için yalnızca.<br /><br /> **Not** bu seçeneği, kod sihirbazları kullanarak ATL ATL nesneleri ekleme desteği göstermez. Yalnızca ATL projeler için ATL nesneler ekleyebilir veya ATL ile MFC projeleri destekler.|  
|**MFC**|Microsoft Foundation Class (MFC) kitaplığı için proje desteği içine derler. Win32 konsol uygulamaları ve yalnızca statik kitaplıklar için.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Win32 Uygulama Sihirbazı](../windows/win32-application-wizard.md)   