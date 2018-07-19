---
title: Giriş ve bitiş kodu yazmada dikkat edilmesi gerekenler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- stack frame layout
- prolog code
- epilog code
- __LOCAL_SIZE constant
- stack, stack frame layout
ms.assetid: c7814de2-bb5c-4f5f-96d0-bcfd2ad3b182
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b7f4e2c25d7ead3399020221c1e0e9633557d24
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37942113"
---
# <a name="considerations-for-writing-prologepilog-code"></a>Giriş ve Bitiş Kodu Yazmada Dikkat Edilmesi Gerekenler
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Kendi giriş ve sonuç kod dizilerinizi yazmadan önce, yığın çerçevesinin nasıl düzenlendiğini anlamak önemlidir. __Local_sıze sembol nasıl kullanılacağını kullanışlıdır.  
  
##  <a name="_pluslang_c.2b2b_.stack_frame_layout"></a> Yığın çerçevesi düzeni  
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
  
 Yığın her zaman aşağı doğru (yüksek bellek adreslerinden düşük olanlara) büyür. Taban işaretçisi (`ebp`) `ebp`'nin gönderilen değerine işaret eder. Yerel alan başlangıcı `ebp-4`. Yerel değişkenlere erişmek için uygun değeri `ebp`'den çıkararak `ebp`'den bir uzaklık hesaplayın.  
  
##  <a name="_pluslang___local_size"></a> __LOCAL_SIZE  
 Derleyici, __local_sıze, işlev giriş kodunun satır içi assembler bloğunu kullanmak için bir simge sağlar. Bu simge, özel giriş kodundaki yığın çerçevesinde yerel değişkenler için alan ayırmak için kullanılır.  
  
 Derleyici __local_sıze değerini belirler. Değerini bayt tüm kullanıcı tanımlı yerel değişkenlerin ve derleyici tarafından oluşturulan geçici değişkenlerin toplam sayısıdır. __Local_sıze yalnızca bir anlık işlenen kullanılabilir. bir ifadede kullanılamaz. Değiştirmemeli veya değeri bu simgeyi yeniden tanımlama. Örneğin:  
  
```  
mov        eax, __LOCAL_SIZE           ;Immediate operand--Okay  
mov        eax, [ebp - __LOCAL_SIZE]   ;Error  
```  
  
 Özel giriş ve sonuç dizileri içeren çıplak bir işlev, aşağıdaki örnekte giriş dizisinde __local_sıze sembol kullanır:  
  
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
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Naked İşlevi Çağrıları](../cpp/naked-function-calls.md)