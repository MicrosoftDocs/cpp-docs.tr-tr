---
title: DLL'leri Yüklemede Gecikme Kısıtlamaları
ms.date: 11/04/2016
helpviewer_keywords:
- constraints [C++], delayed loading of DLLs
- delayed loading of DLLs, constraints
- DLLs [C++], constraints
ms.assetid: 0097ff65-550f-4a4e-8ac3-39bf6404f926
ms.openlocfilehash: be5e5eb360f80e0b2ea9682f38f6787044cd3c63
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493066"
---
# <a name="constraints-of-delay-loading-dlls"></a>DLL'leri Yüklemede Gecikme Kısıtlamaları

İçeri aktarmaların gecikmeli yüklenmesine ilişkin kısıtlamalar vardır.

- Verilerin içeri aktarmaları desteklenemez. Geçici bir çözüm, `LoadLibrary` (veya `GetModuleHandle` gecikme Yükleme Yardımcısı 'nın dll 'yi `GetProcAddress`yüklemiş olduğunu öğrendikten sonra), verileri doğrudan içeri aktarmayı açıkça işleymaktır.

- Kernel32. dll yükleme gecikmesi desteklenmiyor. Bu DLL, Gecikmeli Yükleme Yardımcısı yordamları için gecikme yükleme işlemini gerçekleştirmeye yönelik gereklidir.

- İletilen giriş noktalarının [bağlanması](binding-imports.md) desteklenmiyor.

- Gecikmeli yüklenen DLL 'nin giriş noktasında gerçekleşen işlem başına başlatma işlemleri varsa, DLL 'nin gecikmesi, işlemin aynı davranış ile sonuçlanmayabilir. Diğer durumlarda, DLL aracılığıyla `LoadLibrary`yüklendiğinde işlenmemiş TLS (iş parçacığı yerel depolaması) kullanılarak, [__declspec (thread)](../../cpp/thread.md)kullanılarak bildirilmiştir. ,,, Ve `TlsAlloc` `TlsGetValue` `TlsFree` kullanan`TlsSetValue`dinamik TLS, statik veya Gecikmeli yüklenen dll 'lerde kullanılmaya devam etmektedir.

- Statik (genel) işlev işaretçileri, işleve ilk çağrıdan sonra içeri aktarılan işlevlere yeniden başlatılacak. Bunun nedeni, işlev işaretçisinin ilk kullanımı, dönüştürücü 'e işaret edecektir.

- Normal içeri aktarma mekanizmasını kullanırken, bir DLL 'den yalnızca belirli prosedürleri yüklemeyi geciktirmenin bir yolu yoktur.

- Özel çağırma kuralları (x86 mimarilerinde koşul kodlarını kullanma gibi) desteklenmez. Ayrıca, kayan nokta kayıtları herhangi bir platformda kaydedilmez. Özel yardımcı yordamınız veya kanca yordamlarınız kayan nokta türlerini kullanıyorsa, çağırma kurallarını, kayan nokta parametreleriyle Kaydet ' i içeren makinelerde kayan nokta durumunu tamamen kaydedip geri yüklemesi gerekir. Yardım işlevindeki bir sayısal veri işlemcisi (NDP) yığınında kayan nokta parametreleri alan CRT işlevlerini çağırırsanız, CRT DLL 'yi yükleme gecikmesi konusunda dikkatli olun.

## <a name="see-also"></a>Ayrıca bkz.

[Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](linker-support-for-delay-loaded-dlls.md)<br/>
[LoadLibrary işlevi](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw)<br/>
[GetModuleHandle işlevi](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulehandlew)<br/>
[GetProcAddress işlevi](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)<br/>
[TlsAlloc işlevi](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc)<br/>
[TlsFree işlevi](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsfree)<br/>
[TlsGetValue işlevi](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue)<br/>
[TlsSetValue işlevi](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlssetvalue)
