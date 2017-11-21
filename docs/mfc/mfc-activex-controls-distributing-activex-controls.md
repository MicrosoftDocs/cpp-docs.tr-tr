---
title: "MFC ActiveX denetimleri: ActiveX denetimlerini dağıtma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetWindowsDirectory
- GetSystemDirectory
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], ANSI or Unicode versions
- RegSvr32.exe
- MFC ActiveX controls [MFC], distributing
- distributing MFC ActiveX controls
- redistributable files, MFC ActiveX controls
- GetSystemDirectory method [MFC]
- registering ActiveX controls
- MSVCRT40.dll
- registry [MFC], registering controls
- LoadLibrary method, registering ActiveX controls
- MFC40U.DLL
- MFC40.DLL
- GetWindowsDirectory method [MFC]
- installing ActiveX controls
- GetProcAddress method, registering ActiveX controls
- MFC ActiveX controls [MFC], installing
- MFC ActiveX controls [MFC], registering
- registering controls
- OLEPRO32.DLL
ms.assetid: cd70ac9b-f613-4879-9e81-6381fdfda2a1
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dfd818a22bb720ef41ab1a1dbacc1cd6ee6676b2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-activex-controls-distributing-activex-controls"></a>MFC ActiveX Denetimleri: ActiveX Denetimlerini Dağıtma
Bu makalede ActiveX denetimlerini yeniden dağıtma için ilgili çeşitli sorunlar ele alınmıştır:  
  
-   [ANSI veya Unicode denetim sürümleri](#_core_ansi_or_unicode_control_versions)  
  
-   [ActiveX denetimleri ve yeniden dağıtılabilir DLL'leri yükleme](#_core_installing_activex_controls_and_redistributable_dlls)  
  
-   [Denetimleri kaydetme](#_core_registering_controls)  
  
##  <a name="_core_ansi_or_unicode_control_versions"></a>ANSI veya Unicode denetim sürümleri  
 ANSI veya Unicode bir sürüm denetim ya da her ikisini de dağıtmayı karar vermeniz gerekir. Bu karara ANSI ve Unicode karakter kümesi yapısında taşınabilirlik faktörleri temel alır.  
  
 Tüm Win32 işletim sistemlerinde çalışabilir, ANSI denetimleri çeşitli Win32 işletim sistemleri arasında en fazla taşınabilirlik izin verir. Unicode denetimleri yalnızca Windows NT (3.51 veya sonraki bir sürümü), ancak Windows 95 veya Windows 98 üzerinde çalışır. Taşınabilirlik birincil önceliğiniz, sevk ANSI denetimleri ise. Denetimleri yalnızca Windows NT üzerinde çalıştırırsanız, Unicode denetimleri gönderebilirsiniz. Her ikisi de sevk ve kullanıcının işletim sistemi için en uygun sürümünü yükleyin, uygulamaya sahip seçebilir.  
  
##  <a name="_core_installing_activex_controls_and_redistributable_dlls"></a>ActiveX denetimleri ve yeniden dağıtılabilir DLL'leri yükleme  
 ActiveX denetimleri ile sağladığınız Kurulum programı Windows dizinin özel bir alt dizini oluşturmak ve denetimleri yükleyin. OCX dosyaları.  
  
> [!NOTE]
>  Windows kullanan **GetWindowsDirectory** Windows dizinin adını almak için Kurulum programı API. Alt dizin adı, şirketinizi veya ürününüzü adından türetilen isteyebilirsiniz.  
  
 Kurulum programı gerekli redistributable DLL dosyaları Windows sistem dizininde yüklemeniz gerekir. DLL zaten kullanıcının makinesinde varsa, Kurulum programı sürümlerine yüklemekte olduğunuz sürümleriyle karşılaştırmanız gerekir. Yalnızca sürüm numarası zaten yüklü dosyadan daha yüksek olduğunda bir dosyayı yeniden yükleyin.  
  
 ActiveX denetimleri yalnızca OLE kapsayıcı uygulamaları kullanılabildiğinden, tamamını OLE DLL'leri denetimleri ile dağıtmak için gerek yoktur. İçeren uygulama (veya işletim sistemi) standart OLE yüklü DLL'leri olduğunu kabul edilebilir.  
  
##  <a name="_core_registering_controls"></a>Denetimleri kaydetme  
 Uygun girişleri denetim kullanılabilmesi için Windows kayıt veritabanında oluşturulmalıdır. Bazı ActiveX denetimi kapsayıcıları için kullanıcıların yeni denetimler kaydetmek menü öğesi sağlasa da, bu özellik tüm kapsayıcıları kullanılabilir durumda olmayabilir. Bu nedenle, yüklendiklerinde denetimleri kaydetmek için Kurulum programı isteyebilirsiniz.  
  
 İsterseniz, Denetim bunun yerine doğrudan kaydetmek için Kurulum programı yazabilirsiniz.  
  
 Kullanım **LoadLibrary** Windows API'ı denetimi DLL yüklenemiyor. Ardından, kullanın **GetProcAddress** "DllRegisterServer" işlevi adresini elde edin. Son olarak, arama `DllRegisterServer` işlevi. Aşağıdaki kod örneği, olası bir yöntemi gösterir nerede `hLib` denetim kitaplığı tanıtıcısı depolar ve `lpDllEntryPoint` "DllRegisterServer" işlevin adresini depolar.  
  
 [!code-cpp[NVC_MFC_AxCont#16](../mfc/codesnippet/cpp/mfc-activex-controls-distributing-activex-controls_1.cpp)]  
  
 Denetimi doğrudan kaydetme avantajı, çağırma ve ayrı bir işlemde (yani, REGSVR32) yüklemek yükleme süresini azaltma değil olmanızdır. Ayrıca, kayıt iç işlem olduğundan, Kurulum programı hataları işleyebilir ve öngörülemeyen durumlarda bir dış işlem iyi olabilir.  
  
> [!NOTE]
>  ActiveX denetimi, Kurulum programı yüklemeden önce çağırmalıdır **OleInitialize**. Kurulum programı tamamlandığında, çağrı **OleUnitialize**. Bu ActiveX denetimini kaydettirmek için uygun durumda OLE sistem DLL'leri olan sağlar.  
  
 MFCx0.DLL kaydetmeniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)

