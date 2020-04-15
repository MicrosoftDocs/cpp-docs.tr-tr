---
title: 'MFC ActiveX Denetimleri: ActiveX Denetimlerini Dağıtma'
ms.date: 09/12/2018
f1_keywords:
- GetWindowsDirectory
- GetSystemDirectory
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
ms.openlocfilehash: 1ada1c801b2d9d62f1cc4cd5bf72a2995225b3de
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364622"
---
# <a name="mfc-activex-controls-distributing-activex-controls"></a>MFC ActiveX Denetimleri: ActiveX Denetimlerini Dağıtma

Bu makalede, ActiveX denetimlerinin yeniden dağıtılmasıyla ilgili çeşitli konular tartışılmıştır:

- [ANSI veya Unicode Denetim Sürümleri](#_core_ansi_or_unicode_control_versions)

- [ActiveX Denetimlerinin Yüklenmesi ve Yeniden Dağıtılabilir DL'lerin Yüklenmesi](#_core_installing_activex_controls_and_redistributable_dlls)

- [Denetimleri Kaydetme](#_core_registering_controls)

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. ActiveX'in yerini alabilecek modern teknolojiler hakkında daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

## <a name="ansi-or-unicode-control-versions"></a><a name="_core_ansi_or_unicode_control_versions"></a>ANSI veya Unicode Denetim Sürümleri

Kontrolün ANSI veya Unicode sürümünü gönderip göndermemeye karar vermelisiniz. Bu karar, ANSI ve Unicode karakter kümelerinin doğasında bulunan taşınabilirlik faktörlerine dayanmaktadır.

Tüm Win32 işletim sistemlerinde çalışan ANSI denetimleri, çeşitli Win32 işletim sistemleri arasında maksimum taşınabilirlik sağlar. Unicode denetimleri yalnızca Windows NT'de (sürüm 3.51 veya sonraki sürüm) çalışır, ancak Windows 95 veya Windows 98'de çalışmaz. Taşınabilirlik birincil endişe ise, gemi ANSI kontrolleri. Denetimleriniz yalnızca Windows NT'de çalışacaksa, Unicode denetimlerini yönetebilirsiniz. Ayrıca, her ikisini de göndermeyi seçebilir ve uygulamanızın kullanıcının işletim sistemi için en uygun sürümü yüklemesini sağlayabilirsiniz.

## <a name="installing-activex-controls-and-redistributable-dlls"></a><a name="_core_installing_activex_controls_and_redistributable_dlls"></a>ActiveX Denetimlerinin Yüklenmesi ve Yeniden Dağıtılabilir DL'lerin Yüklenmesi

ActiveX denetimlerinizle sağladığınız kurulum programı, Windows dizininin özel bir alt dizini oluşturmalı ve denetimleri yüklemelidir. OCX dosyaları içinde.

> [!NOTE]
> Windows dizininin adını almak için kurulum programınızdaki Windows `GetWindowsDirectory` API'sını kullanın. Alt dizin adını şirketinizin veya ürününüzün adından türetmek isteyebilirsiniz.

Kurulum programı, Windows sistem dizininde gerekli yeniden dağıtılabilir DLL dosyalarını yüklemelidir. Kullanıcının makinesinde DL'lerden herhangi biri zaten mevcutsa, kurulum programı sürümlerini yüklediğiniz sürümlerle karşılaştırmalıdır. Bir dosyayı yalnızca sürüm numarası zaten yüklenmiş olan dosyadan daha yüksekse yeniden yükleyin.

ActiveX denetimleri yalnızca OLE kapsayıcı uygulamalarında kullanılabildiği için, tüm OLE DL'leri denetimlerinizle dağıtmaya gerek yoktur. İçerdiği uygulamanın (veya işletim sisteminin kendisinin) standart OLE DLL'lerinin yüklü olduğunu varsayabilirsiniz.

## <a name="registering-controls"></a><a name="_core_registering_controls"></a>Denetimleri Kaydetme

Denetimin kullanılabilmesi için windows kayıt veritabanında bunun için uygun girişler oluşturulmalıdır. Bazı ActiveX denetim kapları kullanıcıların yeni denetimleri kaydetmesi için bir menü öğesi sağlar, ancak bu özellik tüm kapsayıcılarda kullanılamayabilir. Bu nedenle, kurulum programınızın denetimleri yüklendiklerinde kaydetmesini isteyebilirsiniz.

İsterseniz, bunun yerine denetimi doğrudan kaydetmek için kurulum programınızı yazabilirsiniz.

Denetim `LoadLibrary` DLL yüklemek için Windows API kullanın. Ardından, `GetProcAddress` "DllRegisterServer" işlevinin adresini almak için kullanın. Son olarak, `DllRegisterServer` işlevi arayın. Aşağıdaki kod örneği, denetim kitaplığı `hLib` tutamacını depoladığı ve `lpDllEntryPoint` "DllRegisterServer" işlevinin adresini depoladığı olası bir yöntemi gösterir.

[!code-cpp[NVC_MFC_AxCont#16](../mfc/codesnippet/cpp/mfc-activex-controls-distributing-activex-controls_1.cpp)]

Denetimi doğrudan kaydetmenin avantajı, yükleme süresini azaltarak ayrı bir işlemi (REGSVR32) çağırmak ve yüklemeniz gerekmemesidir. Buna ek olarak, kayıt dahili bir işlem olduğundan, kurulum programı hataları ve öngörülemeyen durumları dış işlemden daha iyi işleyebilir.

> [!NOTE]
> Kurulum programınız ActiveX denetimini yüklemeden `OleInitialize`önce . Kurulum programınız bittiğinde, `OleUnitialize`'yi arayın. Bu, OLE sistem DL'lerinin ActiveX denetimini kaydetmek için uygun durumda olmasını sağlar.

MFCx0.DLL'yi kaydedin.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)
