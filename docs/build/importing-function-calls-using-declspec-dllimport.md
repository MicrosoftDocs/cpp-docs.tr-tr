---
title: "__Declspec(dllimport) kullanarak işlev çağrılarını içeri aktarma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __declspec
- dllimport
dev_langs: C++
helpviewer_keywords:
- importing function calls [C++]
- dllimport attribute [C++], function call imports
- __declspec(dllimport) keyword [C++]
- function calls [C++], importing
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d1501506d4575c5f7fe1ff1dc7823cbd1545b974
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="importing-function-calls-using-declspecdllimport"></a>__declspec(dllimport) Kullanarak İşlev Çağrılarını İçeri Aktarma
Aşağıdaki kod örneğinde nasıl kullanılacağını gösterir **_declspec(dllimport)** işlev çağrıları, bir uygulamaya DLL'den dışarı aktarmak için. Varsayımında `func1` içeren .exe dosyasından ayrı bir DLL bulunan bir işlevi olduğunu **ana** işlevi.  
  
 Olmadan **__declspec(dllimport)**, bu kodu verilir:  
  
```  
int main(void)   
{  
   func1();  
}  
```  
  
 Derleyici şuna benzer bir kod oluşturur:  
  
```  
call func1  
```  
  
 ve şöyle bir şey çağrıyı bağlayıcı çevirir:  
  
```  
call 0x4000000         ; The address of 'func1'.  
```  
  
 Varsa `func1` adresinin ne bilerek hiçbir şekilde sahip olduğu başka bir DLL'de bağlayıcı bunu doğrudan çözümleyemez `func1` değil. 16 bit ortamlarda, bağlayıcı yükleyicisi doğru adresle çalışma zamanında düzeltme ekini uygulayacağı .exe dosyası bir listede bu kod adresini ekler. 32 bit ve 64-bit ortamlarda, bağlayıcı hangi adresi bilen dönüştürücü oluşturur. Bir 32 bit ortamda dönüştürücü aşağıdakine benzer:  
  
```  
0x40000000:    jmp DWORD PTR __imp_func1  
```  
  
 Burada `imp_func1` adresidir `func1` .exe dosyası içeri aktarma adres tablosunu yuvasında. Tüm adresler böylece bağlayıcıya olarak bilinir. Yükleyici her şeyin doğru şekilde çalışması yükleme zamanında .exe dosyasının içeri aktarma adres tablosunu güncelleştirmek yalnızca vardır.  
  
 Bu nedenle, kullanarak **__declspec(dllimport)** gerekli değilse bağlayıcı dönüştürücü oluşturmaz olduğundan daha iyidir. Dönüştürücüler kodu daha büyük hale (RISC sistemlerinde, bu çok yönerge olabilir) ve önbellek performansı düşürebilir. Derleyici DLL'de işlevidir bildirirseniz, bu dolaylı bir çağrı sizin için oluşturur.  
  
 Artık bu kodu:  
  
```  
__declspec(dllimport) void func1(void);  
int main(void)   
{  
   func1();  
}  
```  
  
 Bu yönergeyi oluşturur:  
  
```  
call DWORD PTR __imp_func1  
```  
  
 Dönüştürücü ve Hayır `jmp` böylece kodu daha küçük ve daha hızlı yönerge.  
  
 Diğer taraftan, DLL içinden işlev çağrıları için dolaylı çağrı kullanmak zorunda istediğiniz değil. Bir işlevin adresi zaten biliyor. Yük ve Dolaylı çağrıdan önce işlevin adresini depolamak için zaman ve yer gerekli olduğundan, doğrudan çağrı her zaman daha hızlı ve daha küçük. Yalnızca kullanmak istediğiniz **__declspec(dllimport)** DLL işlevlerini DLL dışında çağrılırken. Kullanmayın **__declspec(dllimport)** bu DLL oluştururken DLL içindeki işlevlerde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir uygulamaya aktarma](../build/importing-into-an-application.md)