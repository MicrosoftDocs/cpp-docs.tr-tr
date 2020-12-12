---
description: 'Daha fazla bilgi edinin: DLL yükleme gecikmesi kısıtlamaları'
title: DLL'leri Yüklemede Gecikme Kısıtlamaları
ms.date: 11/04/2016
helpviewer_keywords:
- constraints [C++], delayed loading of DLLs
- delayed loading of DLLs, constraints
- DLLs [C++], constraints
ms.assetid: 0097ff65-550f-4a4e-8ac3-39bf6404f926
ms.openlocfilehash: 45f54ca57b57bc689752a8aa80f4c03bbe096817
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197016"
---
# <a name="constraints-of-delay-loading-dlls"></a>DLL'leri Yüklemede Gecikme Kısıtlamaları

İçeri aktarmaların gecikmeli yüklenmesine ilişkin kısıtlamalar vardır.

- Verilerin içeri aktarmaları desteklenemez. Geçici bir çözüm, `LoadLibrary` (veya `GetModuleHandle` gecikme Yükleme Yardımcısı 'nın dll 'yi yüklemiş olduğunu öğrendikten sonra), verileri doğrudan içeri aktarmayı açıkça işleymaktır `GetProcAddress` .

- Kernel32.dll yükleme gecikmesi desteklenmez. Bu DLL, Gecikmeli Yükleme Yardımcısı yordamları için gecikme yükleme işlemini gerçekleştirmeye yönelik gereklidir.

- İletilen giriş noktalarının [bağlanması](binding-imports.md) desteklenmiyor.

- Gecikmeli yüklenen DLL 'nin giriş noktasında gerçekleşen işlem başına başlatma işlemleri varsa, DLL 'nin gecikmesi, işlemin aynı davranış ile sonuçlanmayabilir. Diğer durumlarda, DLL aracılığıyla yüklendiğinde işlenmemiş TLS (iş parçacığı yerel depolaması), [__declspec (iş parçacığı)](../../cpp/thread.md)kullanılarak bildirilmiştir `LoadLibrary` . ,,, Ve kullanan dinamik TLS, `TlsAlloc` `TlsFree` `TlsGetValue` `TlsSetValue` statik veya Gecikmeli yüklenen dll 'lerde kullanılmaya devam etmektedir.

- Statik (genel) işlev işaretçileri, işleve ilk çağrıdan sonra içeri aktarılan işlevlere yeniden başlatılacak. Bunun nedeni, işlev işaretçisinin ilk kullanımı, dönüştürücü 'e işaret edecektir.

- Normal içeri aktarma mekanizmasını kullanırken, bir DLL 'den yalnızca belirli prosedürleri yüklemeyi geciktirmenin bir yolu yoktur.

- Özel çağırma kuralları (x86 mimarilerinde koşul kodlarını kullanma gibi) desteklenmez. Ayrıca, kayan nokta kayıtları herhangi bir platformda kaydedilmez. Özel yardımcı yordamınız veya kanca yordamlarınız kayan nokta türlerini kullanıyorsa, çağırma kurallarını, kayan nokta parametreleriyle Kaydet ' i içeren makinelerde kayan nokta durumunu tamamen kaydedip geri yüklemesi gerekir. Yardım işlevindeki bir sayısal veri işlemcisi (NDP) yığınında kayan nokta parametreleri alan CRT işlevlerini çağırırsanız, CRT DLL 'yi yükleme gecikmesi konusunda dikkatli olun.

## <a name="see-also"></a>Ayrıca bkz.

[Delay-Loaded dll 'Ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)<br/>
[LoadLibrary işlevi](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw)<br/>
[GetModuleHandle işlevi](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulehandlew)<br/>
[GetProcAddress işlevi](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)<br/>
[TlsAlloc işlevi](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc)<br/>
[TlsFree işlevi](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsfree)<br/>
[TlsGetValue işlevi](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue)<br/>
[TlsSetValue işlevi](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlssetvalue)
