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
ms.openlocfilehash: 55ae50d849a67da69cde6a9c4b1529c34ee4b428
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="application-settings-win-32-project-wizard"></a>Uygulama Ayarları, Win 32 Proje Sihirbazı
Win32 Proje seçeneklerini ayarlamak için sihirbazın bu sayfayı kullanın.  
  
 **Uygulama türü**  
 Belirtilen uygulama türü oluşturur.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Konsol uygulaması**|Bir konsol uygulaması oluşturur. Konsol programları ile geliştirilen [konsol işlevleri](https://msdn.microsoft.com/en-us/library/ms813137.aspx), konsol Windows'ta karakter modu desteği sağlar. Visual C++ [çalışma zamanı kitaplıkları](../c-runtime-library/c-run-time-library-reference.md) de çıktı sağlayın ve standart g/ç işlevlerle konsol Windows'dan gibi giriş **printf_s()** ve **scanf_s()**. Bir konsol uygulaması grafik kullanıcı arabirimi olmadan sahiptir. Bir .exe dosyasına kaydeder ve komut satırından bağımsız bir uygulama olarak çalıştırabilirsiniz.<br /><br /> MFC ve ATL bir konsol uygulaması için destek ekleyebilirsiniz.|  
|**Windows uygulaması**|Win32 programı oluşturur. Win32 programı C veya C++, bir grafik kullanıcı arabirimi oluşturmak için Win32 API çağrıları kullanılarak yazılmış bir yürütülebilir (EXE) uygulamasıdır.<br /><br /> MFC eklenemez veya ATL desteği için bir Windows uygulaması.|  
|**DLL**|Win32 dinamik bağlantı kitaplığı (DLL) oluşturur. Win32 DLL C veya C++ çağrıları Win32 API yerine MFC sınıfları kullanan ve, aynı anda birden çok uygulama tarafından kullanılan işlevlerin paylaşılan bir kitaplık gibi davranır yazılmış ikili bir dosyadır.<br /><br /> MFC eklenemez veya ATL desteği DLL uygulamaya. DLL simgeleri dışarı aktarmaları belirtebilirsiniz.|  
|**Statik kitaplığı**|Bir statik kitaplık oluşturur. Bir statik kitaplık nesneleri ve işlevleri ve yürütülebilir dosyanın yapılandırıldığında, programınıza bağlanan veri içeren bir dosyadır. Bu konu starter dosyalarının nasıl oluşturulacağını açıklar ve [proje özellikleri](../ide/property-pages-visual-cpp.md) statik kitaplık için. Bir statik kitaplık dosyası şu avantajları sağlar:<br /><br /> -Bir Win32 statik kitaplık, üzerinde çalıştığınız uygulama Win32 API yerine MFC sınıfları çağrılar yararlıdır.<br />-Windows uygulamanızı kalan C veya C++ yazılmış olup olmadığını bağlama işlemini aynıdır.<br />MFC tabanlı bir program veya bir MFC dışı programı-statik kitaplık bağlayabilirsiniz.|  
  
 **Ek Seçenekler**  
 İlgili destek ve kendi türüne bağlı olarak uygulama seçeneklerini tanımlar.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Boş proje**|Proje dosyalarını boş olduğunu belirtir. Kaynak kodu dosyaları (örneğin, .cpp dosyaları, üst bilgi dosyaları, simgeler, araç çubukları, iletişim kutuları ve benzeri) kümesi varsa ve Visual C++ geliştirme ortamında bir projeyi oluşturmak istediğiniz gerekir önce boş bir proje oluşturun ve ardından dosyaları projeye ekleyin.<br /><br /> Bu seçim, statik kitaplık projeleri için kullanılamaz.|  
|**Sembolleri dışa aktarma**|DLL projesi simgeleri aktarır belirtir.|  
|**Önceden derlenmiş üst bilgi**|Statik kitaplık proje önceden derlenmiş üstbilgi kullandığını belirtir.|  
|Güvenlik geliştirme yaşam döngüsü (SDL) denetler|SDL hakkında daha fazla bilgi için bkz: [Microsoft Security Development Lifecycle (SDL) işlem kılavuzu](../build/reference/sdl-enable-additional-security-checks.md)|  
  
 **Desteği ekleme**  
 Visual C++'da sağlanan kitaplıklarından birini desteği ekleyin.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**ATL**|Etkin Şablon kitaplığı (ATL) içinde sınıflar için proje desteği içine oluşturur. Win32 konsol uygulamaları için yalnızca.<br /><br /> **Not** bu seçeneği ATL kullanarak ATL nesneleri kod sihirbazları ekleme desteği göstermez. MFC projeleri ATL ile desteklemek veya yalnızca ATL projeleri için ATL nesneleri ekleyebilirsiniz.|  
|**MFC**|Microsoft Foundation Class (MFC) kitaplığı için proje desteği içine oluşturur. Win32 konsol uygulamaları ve yalnızca statik kitaplıklar için.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Win32 Uygulama Sihirbazı](../windows/win32-application-wizard.md)   
