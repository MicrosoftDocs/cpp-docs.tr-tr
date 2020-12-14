---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: ActiveX denetimlerini dağıtma'
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
ms.openlocfilehash: faf85bffd9911c38764aea19d1ddb682fd719be1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280722"
---
# <a name="mfc-activex-controls-distributing-activex-controls"></a>MFC ActiveX Denetimleri: ActiveX Denetimlerini Dağıtma

Bu makalede, ActiveX denetimlerini yeniden dağıtma ile ilgili çeşitli sorunlar ele alınmaktadır:

- [ANSI veya Unicode denetim sürümleri](#_core_ansi_or_unicode_control_versions)

- [ActiveX denetimleri ve yeniden dağıtılabilir DLL 'Ler yükleme](#_core_installing_activex_controls_and_redistributable_dlls)

- [Denetimleri kaydetme](#_core_registering_controls)

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

## <a name="ansi-or-unicode-control-versions"></a><a name="_core_ansi_or_unicode_control_versions"></a> ANSI veya Unicode denetim sürümleri

Denetimin bir ANSI veya Unicode sürümünü mi yoksa her ikisinin mi gönderileceğine karar vermelisiniz. Bu karar, ANSI ve Unicode karakter kümelerinde devralınan taşınabilirlik faktörlerini temel alır.

Tüm Win32 işletim sistemlerinde çalışan ANSI denetimleri, çeşitli Win32 işletim sistemleri arasında en fazla taşınabilirlik için izin verir. Unicode denetimleri yalnızca Windows NT (sürüm 3,51 veya üzeri) üzerinde çalışır, ancak Windows 95 veya Windows 98 üzerinde değildir. Taşınabilirlik birincil endişeniz ise ANSI denetimleri sunun. Denetimleriniz yalnızca Windows NT üzerinde çalışıyorsa, Unicode denetimleri gönderebilirsiniz. Ayrıca, her ikisini de yüklemeyi seçebilir ve uygulamanızın kullanıcının işletim sistemi için en uygun sürümü yüklemesini sağlayabilirsiniz.

## <a name="installing-activex-controls-and-redistributable-dlls"></a><a name="_core_installing_activex_controls_and_redistributable_dlls"></a> ActiveX denetimleri ve yeniden dağıtılabilir DLL 'Ler yükleme

ActiveX denetimleriniz ile sağladığınız Kurulum programı Windows dizininin özel bir alt dizinini oluşturmalı ve denetimleri yüklemelidir. İçindeki OCX dosyaları.

> [!NOTE]
> `GetWindowsDirectory`Windows dizininin adını almak için kurulum programınızdaki Windows API 'sini kullanın. Alt dizin adını şirketinizin veya ürününüzün adından türetmek isteyebilirsiniz.

Kurulum programı, gerekli yeniden dağıtılabilir DLL dosyalarını Windows sistem dizinine yüklemelidir. Dll 'Lerden herhangi biri zaten kullanıcının makinesinde mevcutsa, Kurulum programı sürümlerini yüklemekte olduğunuz sürümlerle karşılaştırmalıdır. Yalnızca sürüm numarası yüklü olan dosyadan daha yüksek olduğunda bir dosyayı yeniden yükleyin.

ActiveX denetimleri yalnızca OLE kapsayıcı uygulamalarında kullanılabileceği için, tüm OLE dll kümesini denetimleriniz ile dağıtmanız gerekmez. Kapsayan uygulamanın (veya işletim sisteminin kendisi) standart OLE dll 'Lerinin yüklü olduğunu varsayabilirsiniz.

## <a name="registering-controls"></a><a name="_core_registering_controls"></a> Denetimleri kaydetme

Bir denetim kullanılmadan önce, Windows kayıt veritabanında bu için uygun girişlerin oluşturulması gerekir. Bazı ActiveX denetim kapsayıcıları, kullanıcıların yeni denetimleri kaydetmesi için bir menü öğesi sağlar, ancak bu özellik tüm kapsayıcılarda kullanılamayabilir. Bu nedenle, kurulum programınızın denetimleri yüklendiklerinde kaydetmesini isteyebilirsiniz.

İsterseniz, denetimi doğrudan kaydetmek için kurulum programınızı yazabilirsiniz.

`LoadLibrary`DENETIM dll 'sini yüklemek için WINDOWS API 'yi kullanın. Sonra, `GetProcAddress` "DllRegisterServer" işlevinin adresini almak için kullanın. Son olarak, `DllRegisterServer` işlevini çağırın. Aşağıdaki kod örneği, `hLib` Denetim kitaplığının tanıtıcısını depolayan ve `lpDllEntryPoint` "DllRegisterServer" işlevinin adresini depolayan olası bir yöntemi gösterir.

[!code-cpp[NVC_MFC_AxCont#16](codesnippet/cpp/mfc-activex-controls-distributing-activex-controls_1.cpp)]

Denetimi doğrudan kaydetmenin avantajı, yükleme süresini azaltarak ayrı bir işlem (yani, REGSVR32) çağırmanız ve yüklemeniz gerekmez. Ayrıca, kayıt bir iç işlem olduğundan, Kurulum programı hata ve beklenmedik durumları bir dış işlemden daha iyi işleyebilir.

> [!NOTE]
> Kurulum programınız bir ActiveX denetimi yüklemeden önce, çağrısı yapılmalıdır `OleInitialize` . Kurulum programınız tamamlandığında, öğesini çağırın `OleUnitialize` . Bu, OLE sistem dll 'Lerinin ActiveX denetimini kaydettirmek için uygun durumda olmasını sağlar.

MFCx0.DLL kaydetmelisiniz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)
