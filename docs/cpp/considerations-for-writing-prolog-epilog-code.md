---
title: "Giriş bitiş kodu yazmada dikkat edilmesi gerekenler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- stack frame layout
- prolog code
- epilog code
- __LOCAL_SIZE constant
- stack, stack frame layout
ms.assetid: c7814de2-bb5c-4f5f-96d0-bcfd2ad3b182
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9578e106c536f14059be95724ac1c2c9af92f3cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="considerations-for-writing-prologepilog-code"></a>Giriş ve Bitiş Kodu Yazmada Dikkat Edilmesi Gerekenler
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Kendi giriş ve sonuç kod dizilerinizi yazmadan önce, yığın çerçevesinin nasıl düzenlendiğini anlamak önemlidir. Nasıl kullanılacağını öğrenmek de yararlıdır **__local_sıze** simgesi.  
  
##  <a name="_pluslang_c.2b2b_.stack_frame_layout"></a>Yığın çerçevesi düzeni  
 Bu örnekte, 32 bit işlevinde görünebilecek standart giriş kodu gösterilmektedir:  
  
```  
push        ebp                ; Save ebp  
mov         ebp, esp           ; Set stack frame pointer  
sub         esp, localbytes    ; Allocate space for locals  
push        <registers>        ; Save registers  
```  
  
 `localbytes` değişkeni yerel değişkenler için yığında gereken bayt sayısını gösterir, `<registers>` değişkeni ise yığında kaydedilecek yazmaçların listesini gösteren bir yer tutucudur. Yazmaçları gönderdikten sonra, yığın üzerine başka bir uygun veri yerleştirebilirsiniz. Aşağıda ilgili sonuç kodu bulunmaktadır:  
  
```  
pop         <registers>   ; Restore registers  
mov         esp, ebp      ; Restore stack pointer  
pop         ebp           ; Restore ebp  
ret                       ; Return from function  
```  
  
 Yığın her zaman aşağı doğru (yüksek bellek adreslerinden düşük olanlara) büyür. Taban işaretçisi (`ebp`) `ebp`'nin gönderilen değerine işaret eder. Yerel öğeler alanı başlangıcı `ebp-4`. Yerel değişkenlere erişmek için uygun değeri `ebp`'den çıkararak `ebp`'den bir uzaklık hesaplayın.  
  
##  <a name="_pluslang___local_size"></a>__LOCAL_SIZE  
 Bir simge derleyici sağlar **__local_sıze**, işlevi giriş kodu satır içi derleyici bloğunu kullanmak için. Bu simge, yerel değişkenleri özel giriş kodunda yığın çerçevesinde alan ayırmak için kullanılır.  
  
 Derleyici değerini belirler **__local_sıze**. Değerini, tüm kullanıcı tanımlı yerel değişkenleri ve derleyicinin ürettiği geçici değişkenleri bayt toplam sayısıdır. **__Local_sıze** yalnızca hemen işleneni olarak; kullanılabilir bir ifadede kullanılamaz. Değil, değiştirmek veya bu simge değerini yeniden tanımlamanız gerekir. Örneğin:  
  
```  
mov        eax, __LOCAL_SIZE           ;Immediate operand--Okay  
mov        eax, [ebp - __LOCAL_SIZE]   ;Error  
```  
  
 Özel giriş ve bitiş içeren bir çıplak işlev aşağıdaki örneği dizilerinin kullanır **__local_sıze** sembol giriş sırası içinde:  
  
```  
// the__local_size_symbol.cpp  
// processor: x86  
__declspec ( naked ) int main() {  
   int i;  
   int j;  
  
   __asm {      /* prolog */  
      push   ebp  
      mov      ebp, esp  
      sub      esp, __LOCAL_SIZE  
      }  
  
   /* Function body */  
   __asm {   /* epilog */  
      mov      esp, ebp  
      pop      ebp  
      ret  
      }  
}  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Naked İşlevi Çağrıları](../cpp/naked-function-calls.md)