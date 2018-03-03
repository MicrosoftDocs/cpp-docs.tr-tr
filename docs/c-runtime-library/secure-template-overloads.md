---
title: "Güvenli şablon aşırı yüklemeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES
- _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES
- _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT
dev_langs:
- C++
helpviewer_keywords:
- _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES
- _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES
- _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT
- secure template overloads
ms.assetid: 562741d0-39c0-485e-8529-73d740f29f8f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 92ad08738ea2c8c748ac642c5ea15f4b0a257da9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="secure-template-overloads"></a>Güvenli Şablon Aşırı Yüklemeleri
Microsoft Gelişmiş Güvenlik sürümleri lehinde birçok C çalışma zamanı kitaplığı (CRT) işlevler kullanım dışı. Örneğin, `strcpy_s` daha güvenli yerini alır `strcpy`. Kullanım dışı bırakılan işlevler güvenlik hataların genel kaynakları olduklarından belleğin üzerine operations engellemez. Varsayılan olarak, bu işlevler birini kullandığınızda derleyici kullanımdan kaldırma uyarısı oluşturur. CRT C++ şablon aşırı yüklemeleri kolaylığı yardımcı olması bu işlevler için daha güvenli çeşitleri geçiş sağlar.  
  
Örneğin, bu kod parçacığını bir uyarı oluşturur çünkü `strcpy` kullanım dışıdır:  
  
```cpp  
char szBuf[10];  
strcpy(szBuf, "test"); // warning: deprecated  
```
  
Kullanımdan kaldırma uyarısı kodunuzu olmayabilecek söyleyin yoktur. Kodunuzu bellek üzerine yazılamıyor doğruladıysanız, birkaç seçeneğiniz vardır. Uyarıyı göz ardı etmeyi seçebilir, simgenin tanımlayabilirsiniz `_CRT_SECURE_NO_WARNINGS` CRT Include deyimleri önce uyarı veya gizlemek için üstbilgiler kullanmak için kodunuzu güncelleştirebilirsiniz `strcpy_s`:  
  
```cpp  
char szBuf[10];  
strcpy_s(szBuf, 10, "test"); // security-enhanced _s function  
```
  
Şablon aşırı yüklemeleri ek seçenekler sunar. Tanımlarsanız `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` 1, bu şablon aşırı yüklemeleri daha güvenli çeşitleri otomatik olarak çağrı standart CRT işlevleri sağlar. Varsa `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` kodunuzu herhangi bir değişiklik gerekli sonra 1 ' dir. Planda, çağrısı `strcpy` yapılan bir çağrı olarak değiştirilmesini `strcpy_s` otomatik olarak sağlanan boyutu bağımsız değişkeniyle.  
  
```cpp  
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1  
  
// ...  
  
char szBuf[10];  
strcpy(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")  
```  
  
Makro `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` bir sayısı gibi almayan işlevleri etkilemez `strncpy`. Şablon aşırı yüklemeleri sayısı işlevler için etkinleştirmek için tanımlama `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` 1. Bunu yapmadan önce ancak, kodunuzu değil (bir ortak hata) arabellek boyutu olan karakter sayısı geçtiğinden emin olun. Ayrıca, işlev çağrısı güvenli değişken çağrılırsa gereksizdir sonra kod, açıkça null Sonlandırıcı arabellek sonunda yazar. Kesme davranışını gerekirse bkz [_TRUNCATE](../c-runtime-library/truncate.md).  
  
> [!NOTE]
>  Makro `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` gerektiren `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` de 1 olarak tanımlanır. Varsa `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` 1 olarak tanımlanır ve `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` tanımlanan 0 hiçbir şablon aşırı yüklemeleri uygulama gerçekleştirmez.  
  
Tanımladığınızda `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` isteğe bağlı olarak 1'e şablon aşırı yüklemeleri güvenli bir değişken dizisini ("_Yanları içinde" bitiş adları) sağlar. Bu durumda, `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` 1, sonra da özgün kod bir küçük değişiklikler yapılması gerekir.:  
  
```cpp  
#define _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES 1  
  
// ...  
  
char szBuf[10];  
strcpy_s(szBuf, "test"); // ==> strcpy_s(szBuf, 10, "test")  
```  
  
 Yalnızca işlev adı ("_Yanları" ekleyerek); değiştirilmesi gerekiyor Şablon aşırı boyutu bağımsız değişkeniyle sağlama mvc'deki.  
  
 Varsayılan olarak, `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` ve `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT` 0 (devre dışı) tanımlanır ve `_CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES` 1 (etkin) tanımlanır.  
  
 Bu şablon yalnızca iş statik diziler için overloads unutmayın. Dinamik olarak ayrılan arabellek ek kaynak kod değişikliklerini gerektirir. Yukarıdaki örneklerde yeniden ziyaret etme:  
  
```cpp  
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1  
  
// ...  
  
char *szBuf = (char*)malloc(10);  
strcpy(szBuf, "test"); // still deprecated; you have to change it to  
                       // strcpy_s(szBuf, 10, "test");  
```  
  
 Ve bu:  
  
```cpp  
#define _CRT_SECURE_CPP_OVERLOAD_SECURE_NAMES 1  
  
// ...  
  
char *szBuf = (char*)malloc(10);  
strcpy_s(szBuf, "test"); // doesn't compile; you have to change it to  
                         // strcpy_s(szBuf, 10, "test");  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRT'deki güvenlik özellikleri](../c-runtime-library/security-features-in-the-crt.md)   
 [CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)