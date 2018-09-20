---
title: 'MFC ActiveX denetimleri: ActiveX denetimlerini dağıtma | Microsoft Docs'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- GetWindowsDirectory
- GetSystemDirectory
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f067b1835c9ff70c7a7c91d401a83e7fa3e1cce
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382303"
---
# <a name="mfc-activex-controls-distributing-activex-controls"></a>MFC ActiveX Denetimleri: ActiveX Denetimlerini Dağıtma

Bu makalede, ActiveX denetimlerini yeniden dağıtma için ilgili çeşitli sorunlar ele alınmıştır:

- [ANSI veya Unicode denetim sürümleri](#_core_ansi_or_unicode_control_versions)

- [ActiveX denetimleri ve yeniden dağıtılabilir DLL'lerinin yükleme](#_core_installing_activex_controls_and_redistributable_dlls)

- [Denetimlerini kaydetme](#_core_registering_controls)


>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerini modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).

##  <a name="_core_ansi_or_unicode_control_versions"></a> ANSI veya Unicode denetim sürümleri

Bir denetim ya da her ikisini de ANSI veya Unicode sürümü dağıtmayı karar vermeniz gerekir. Bu kararı ANSI ve Unicode karakter kümelerindeki doğal taşınabilirlik etkenlere bağlıdır.

Çeşitli Win32 işletim sistemleri arasında en fazla taşınabilirlik için tüm Win32 işletim sistemlerinde çalışan, ANSI denetimleri sağlar. Unicode denetim, yalnızca Windows NT (sürüm 3.51 sürümü veya üstü), ancak Windows 95 ya da Windows 98 çalışır. Taşınabilirlik, birincil sevk ANSI denetimleri önemliyse. Denetimleri yalnızca Windows NT çalıştıracaksanız, Unicode denetim sevk edebilir. Ayrıca, her ikisi de gönderin ve kullanıcının işletim sistemi için en uygun sürümünü yüklemek uygulamanızı oluşturdunuz seçebilirsiniz.

##  <a name="_core_installing_activex_controls_and_redistributable_dlls"></a> ActiveX denetimleri ve yeniden dağıtılabilir DLL'lerinin yükleme

Kurulum programı, ActiveX denetimleriyle sağlamanız Windows dizininin özel bir alt oluşturun ve denetimleri yükle. İçindeki dosyaların OCX.

> [!NOTE]
>  Windows kullanan `GetWindowsDirectory` Windows dizinin adını almak için Kurulum programınız API. Alt ad şirketinizi veya ürününüzü adından türetilir isteyebilirsiniz.

Kurulum programını yeniden dağıtılabilir gerekli DLL dosyalarının Windows sistem dizininde yüklemeniz gerekir. DLL zaten kullanıcının makinesine varsa, Kurulum programı sürümlerine yüklemekte olduğunuz sürümleri ile karşılaştırmanız gerekir. Yalnızca sürüm numarasının zaten yüklü dosyasından daha yüksekse, bir dosyayı yeniden yükleyin.

ActiveX denetimleri yalnızca OLE kapsayıcı uygulamalarında kullanılabildiğinden OLE DLL'leri denetimleri ile tam kümesini dağıtmak için gerek yoktur. İçeren uygulama (veya işletim sistemi) standart OLE yüklü DLL'leri olduğunu varsayabilirsiniz.

##  <a name="_core_registering_controls"></a> Denetimlerini kaydetme

Uygun girişleri denetim kullanılabilmesi için Windows kayıt defteri veritabanındaki oluşturulmalıdır. Bazı ActiveX denetimi kapsayıcıları için menü öğesi için yeni denetimler kaydedin açmasına sağlasa da, bu özellik tüm kapsayıcılarda kullanılamayabilir. Bu nedenle yüklendiklerinde denetimleri kaydetmek için Kurulum programınıza isteyebilirsiniz.

Tercih ederseniz, bunun yerine denetimi doğrudan kaydetmek için Kurulum programı yazabilirsiniz.

Kullanım `LoadLibrary` Windows API'ı denetim DLL yüklenemedi. Ardından, `GetProcAddress` "DllRegisterServer" işlevin adresini almak için. Son olarak, çağrı `DllRegisterServer` işlevi. Aşağıdaki kod örneği, olası bir yöntemi gösterir burada `hLib` denetim kitaplığı tanıtıcısını depolar ve `lpDllEntryPoint` "DllRegisterServer" işlevin adresini depolar.

[!code-cpp[NVC_MFC_AxCont#16](../mfc/codesnippet/cpp/mfc-activex-controls-distributing-activex-controls_1.cpp)]

Denetimi doğrudan kaydetme avantajı, çağırma ve ayrı bir işlemde (yani, REGSVR32) yüklemek yükleme süresini azaltarak değil olmanızdır. Ayrıca, kayıt bir iç işlem olduğundan, Kurulum programı hataları işleyebilir ve öngörülemeyen durumlarda bir dış işlem iyi olabilir.

> [!NOTE]
>  ActiveX denetimi, Kurulum programı yüklemeden önce çağırmalıdır `OleInitialize`. Kurulum programınıza sona erdiğinde, çağrı `OleUnitialize`. Bu şekilde, bir ActiveX denetimi kaydetmek için uygun durumda OLE sistem DLL'lerini olmasını sağlar.

MFCx0.DLL kaydetmeniz.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

