---
title: Giriş ve bitiş kodu yazarken dikkat edilmesi gerekenler
ms.date: 11/04/2016
helpviewer_keywords:
- layouts, stack frame
- stack frame layout
- __LOCAL_SIZE constant
- stack, stack frame layout
ms.assetid: 3b8addec-e809-48e4-b1d0-5bad133bd4b8
ms.openlocfilehash: 52403fc45bbb68d693ef154bf39c5dd366dd10c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62312531"
---
# <a name="considerations-when-writing-prologepilog-code"></a>Giriş ve Bitiş Kodu Yazarken Dikkat Edilmesi Gerekenler

**Microsoft'a özgü**

Kendi giriş ve sonuç kod dizilerinizi yazmadan önce, yığın çerçevesinin nasıl düzenlendiğini anlamak önemlidir. Nasıl kullanılacağını bilmek yararlıdır **__local_sıze** önceden tanımlanmış sabitinin.

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

Derleyici, bir sabit sağlar **__local_sıze**, işlev giriş kodunun satır içi assembler bloğunu kullanmak için. Bu sabit, özel giriş kodundaki yığın çerçevesinde yerel değişkenler için yer ayırmak üzere kullanılır.

Derleyici değeri belirler **__local_sıze**. Değer, tüm kullanıcı tanımlı yerel değişkenlerin ve derleyici tarafından oluşturulan geçici değişkenlerin toplam bayt sayısıdır. **__Local_sıze** yalnızca bir anlık işlenen olarak; kullanılabilir bir ifadede kullanılamaz. Bu sabitin değerini değiştirmemeli veya yeniden tanımlamamalısınız. Örneğin:

```
mov      eax, __LOCAL_SIZE           ;Immediate operand--Okay
mov      eax, [ebp - __LOCAL_SIZE]   ;Error
```

Aşağıdaki özel giriş ve sonuç içeren çıplak bir işlev örneği kullanan dizilerinin **__local_sıze** giriş dizisinde:

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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Naked İşlevleri](../c-language/naked-functions.md)
