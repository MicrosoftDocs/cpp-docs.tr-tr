---
title: GetProcAddress
ms.date: 11/04/2016
f1_keywords:
- GetProcAddress
helpviewer_keywords:
- DLLs [C++], GetProcAddress
- ordinal exports [C++]
- GetProcAddress method
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
ms.openlocfilehash: 2d322cfe7d3bd60d8d702a226e181eb7b4ede963
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493246"
---
# <a name="getprocaddress"></a>GetProcAddress

DLL 'de verilmiş bir işlevin adresini almak için [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) 'e AÇıKÇA bir dll çağrısına bağlama işlemi. DLL işlevini çağırmak için döndürülen işlev işaretçisini kullanırsınız. **GetProcAddress** , dll modülünün tanıtıcısını ( **LoadLibrary**, `AfxLoadLibrary`veya **GetModuleHandle**tarafından döndürülen) parametre olarak alır ve çağırmak istediğiniz işlevin adını ya da işlevin dışarı aktarma sıra sayısını alır.

DLL işlevini bir işaretçi aracılığıyla çağırırken ve derleme zamanı tür denetimi olmadığından, yığında ayrılan belleği fazla adımla ve erişim ihlaline neden olmayacak şekilde işlevin parametrelerinin doğru olduğundan emin olun. Tür güvenliğini sağlamaya yardımcı olmanın bir yolu, içe aktarılmış işlevlerin işlev prototiptürlerine bakmak ve işlev işaretçileri için eşleşen tür tanımları 'ler oluşturmaktır. Örneğin:

```
typedef UINT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT);
...

HINSTANCE hDLL;               // Handle to DLL
LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer
DWORD dwParam1;
UINT  uParam2, uReturnVal;

hDLL = LoadLibrary("MyDLL");
if (hDLL != NULL)
{
   lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL,
                                           "DLLFunc1");
   if (!lpfnDllFunc1)
   {
      // handle the error
      FreeLibrary(hDLL);
      return SOME_ERROR_CODE;
   }
   else
   {
      // call the function
      uReturnVal = lpfnDllFunc1(dwParam1, uParam2);
   }
}
```

**GetProcAddress** çağrılırken istediğiniz işlevi nasıl BELIRTIRSINIZ, dll 'nin nasıl oluşturulduğuna bağlıdır.

Dışarı aktarma sırasını yalnızca, bağlandığınız DLL bir modül tanımı (. def) dosyası ile derlendiyse ve sıra sayıları DLL 'nin. def dosyasının **dışarı aktarmalar** bölümündeki işlevlerle listeleniyorsa elde edilebilir. İşlev adının aksine, bir dışa aktarma sırası ile **GetProcAddress** çağrısı, dışa aktarma sıraları dll 'nin dışarı aktarma tablosuna dizin olarak görev YAPTıĞıNDAN, dll 'nin dışarı aktarılmış işlevlere sahip olması biraz daha hızlıdır. Dışarı aktarma sırası ile, **GetProcAddress** , BELIRTILEN adı dll 'nin dışarı aktarma tablosundaki işlev adlarıyla karşılaştırmak yerine doğrudan işlevi bulabilir. Ancak, yalnızca. def dosyasındaki dışarı aktarılmış işlevlere sıra sayıları atama üzerinde denetim sahibi olmanız durumunda **GetProcAddress** 'i dışarı aktarma sırası ile çağırmanız gerekir.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Bir yürütülebilir dosyayı DLL’ye bağlama](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Bir yürütülebilir dosyayı DLL’ye bağlama](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [LoadLibrary ve AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary)

- [DEF dosyaları kullanarak DLL 'den dışarı aktarma](exporting-from-a-dll-using-def-files.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C/C++ dll 'Leri oluşturma](dlls-in-visual-cpp.md)
