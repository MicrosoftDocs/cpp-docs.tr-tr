---
title: Giriş bitiş kodu yazarken dikkat edilmesi gerekenler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- layouts, stack frame
- stack frame layout
- __LOCAL_SIZE constant
- stack, stack frame layout
ms.assetid: 3b8addec-e809-48e4-b1d0-5bad133bd4b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd3d63ed06ee07943263e6f8a59bb9fceea4d99d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="considerations-when-writing-prologepilog-code"></a>Giriş ve Bitiş Kodu Yazarken Dikkat Edilmesi Gerekenler
**Microsoft özel**  
  
 Kendi giriş ve sonuç kod dizilerinizi yazmadan önce, yığın çerçevesinin nasıl düzenlendiğini anlamak önemlidir. Nasıl kullanılacağını öğrenmek de yararlıdır **__local_sıze** önceden tanımlanmış sabiti.  
  
##  <a name="_clang_c_stack_frame_layout"></a> C yığın çerçevesi düzeni  
 Bu örnekte, 32 bit işlevinde görünebilecek standart giriş kodu gösterilmektedir:  
  
```  
push     ebp                 ; Save ebp  
mov      ebp, esp            ; Set stack frame pointer  
sub      esp, localbytes     ; Allocate space for locals  
push     <registers>         ; Save registers  
```  
  
 `localbytes` değişkeni yerel değişkenler için yığında gereken bayt sayısını gösterir, `registers` değişkeni ise yığında kaydedilecek yazmaçların listesini gösteren bir yer tutucudur. Yazmaçları gönderdikten sonra, yığın üzerine başka bir uygun veri yerleştirebilirsiniz. Aşağıda ilgili sonuç kodu bulunmaktadır:  
  
```  
pop      <registers>         ; Restore registers  
mov      esp, ebp            ; Restore stack pointer  
pop      ebp                 ; Restore ebp  
ret                          ; Return from function  
```  
  
 Yığın her zaman aşağı doğru (yüksek bellek adreslerinden düşük olanlara) büyür. Taban işaretçisi (`ebp`) `ebp`'nin gönderilen değerine işaret eder. Yerel değişkenler alanı `ebp-2`'de başlar. Yerel değişkenlere erişmek için uygun değeri `ebp`'den çıkararak `ebp`'den bir uzaklık hesaplayın.  
  
##  <a name="_clang_the___local_size_constant"></a> __Local_sıze sabiti  
 Bir sabit derleyici sağlar **__local_sıze**, işlevi giriş kodu satır içi derleyici bloğunu kullanmak için. Bu sabit, özel giriş kodundaki yığın çerçevesinde yerel değişkenler için yer ayırmak üzere kullanılır.  
  
 Derleyici değerini belirler **__local_sıze**. Değer, tüm kullanıcı tanımlı yerel değişkenlerin ve derleyici tarafından oluşturulan geçici değişkenlerin toplam bayt sayısıdır. **__Local_sıze** yalnızca hemen işleneni olarak; kullanılabilir bir ifadede kullanılamaz. Bu sabitin değerini değiştirmemeli veya yeniden tanımlamamalısınız. Örneğin:  
  
```  
mov      eax, __LOCAL_SIZE           ;Immediate operand--Okay  
mov      eax, [ebp - __LOCAL_SIZE]   ;Error  
```  
  
 Özel giriş ve bitiş içeren bir çıplak işlev aşağıdaki örneği dizilerinin kullanır **__local_sıze** Giriş dizisinin:  
  
```  
__declspec ( naked ) func()  
{  
   int i;  
   int j;  
  
   __asm      /* prolog */  
      {  
      push   ebp  
      mov      ebp, esp  
      sub      esp, __LOCAL_SIZE  
      }  
  
   /* Function body */  
  
   __asm      /* epilog */  
      {  
      mov      esp, ebp  
      pop      ebp  
      ret  
      }  
}     
```  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Naked İşlevleri](../c-language/naked-functions.md)