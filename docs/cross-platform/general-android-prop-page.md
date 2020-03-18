---
title: Genel Proje Özellikleri (Android C++)
ms.date: 10/23/2017
ms.assetid: 65f4868b-b864-4989-a275-1e51869ef599
f1_keywords:
- VC.Project.VCConfiguration.Android.OutputDirectory
- VC.Project.VCConfiguration.Android.IntermediateDirectory
- VC.Project.VCConfiguration.Android.TargetName
- VC.Project.VCConfiguration.Android.TargetExt
- VC.Project.VCConfiguration.Android.DeleteExtensionsOnClean
- VC.Project.VCConfiguration.Android.BuildLogFile
- VC.Project.VCConfiguration.Android.PlatformToolset
- VC.Project.VCConfiguration.Android.ConfigurationType
- VC.Project.VCConfiguration.UseOfSTL
- VC.Project.VCConfiguration.ThumbMode
ms.openlocfilehash: 78f6df8286151b61ed026cc6b5170ff3508295d4
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446887"
---
# <a name="general-project-properties-android-c"></a>Genel Proje Özellikleri (Android C++)

| Özellik | Açıklama | Yapabileceği |
|--|--|--|
| Çıkış dizini | Çıkış dosyası dizinine göreli bir yol belirtir; ortam değişkenlerini içerebilir. |
| Ara Dizin | Ara dosya dizinine göreli bir yol belirtir; ortam değişkenlerini içerebilir. |
| Hedef Adı | Bu projenin oluşturduğu bir dosya adı belirtir. |
| Hedef uzantısı | Bu projenin oluşturduğu bir dosya uzantısını belirtir. (Örnek: *. exe* veya *. dll*) |
| Temizlemede Silinecek Uzantılar | Ara dizindeki, temizleme veya yeniden oluşturma sırasında Silinecek dosyalar için noktalı virgülle ayrılmış joker karakter belirtimi. |
| Derleme günlüğü dosyası | Derleme günlüğü etkinken yazılacak olan derleme günlüğü dosyasını belirtir. |
| Platform araç takımı | Geçerli yapılandırmayı oluşturmak için kullanılan araç takımını belirtir; Ayarlanmamışsa, varsayılan araç kümesi kullanılır |
| Yapılandırma türü | Bu yapılandırmanın oluşturduğu çıkışın türünü belirtir. | **Dinamik kitaplık (. so)** -dinamik kitaplık ( *. so*)<br>**Statik kitaplık (. a)** -statik kitaplık ( *. a*)<br>**Yardımcı program** -yardımcı program<br>**Makefile** -makefile<br> |
| Hedef API düzeyi | Bu yapılandırmanın hedeflediği Android NDK API düzeyi. |
| STL kullanımı | Bu yapılandırma C++ için hangi standart kitaplığın kullanılacağını belirtir. | **En C++ az çalışma zamanı kitaplığı (sistem)**<br>**C++çalışma zamanı statik kitaplığı (Gabi + + _static)**<br>**C++çalışma zamanı paylaşılan kitaplığı (Gabi + + _shared)**<br>**STLport çalışma zamanı statik kitaplığı (stlport_static)**<br>**STLport çalışma zamanı paylaşılan kitaplığı (stlport_shared)**<br>**GNU STL statik kitaplığı (gnustl_static)**<br>**GNU STL paylaşılan kitaplığı (gnustl_shared)**<br>**LLVM LIBC + + statik kitaplığı (c++ _static)**<br>**LLVM LIBC + + paylaşılan kitaplığı (c++ _shared)**<br> |
| Thumb modu | Thumb mikro mimarisi için yürütülen kodu oluşturun. Bu yalnızca ARM mimarisi için geçerlidir. | **Resmi**<br>**Uzaklığını**<br>**Devre dışı**<br> |
