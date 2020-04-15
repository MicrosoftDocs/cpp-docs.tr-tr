---
title: Giriş ve Bitiş Kodu Yazarken Dikkat Edilmesi Gerekenler
ms.date: 11/04/2016
helpviewer_keywords:
- layouts, stack frame
- stack frame layout
- __LOCAL_SIZE constant
- stack, stack frame layout
ms.assetid: 3b8addec-e809-48e4-b1d0-5bad133bd4b8
ms.openlocfilehash: e1559c75808a72cd3f9674399bec036cf392b44f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81334589"
---
# <a name="considerations-when-writing-prologepilog-code"></a>Giriş ve Bitiş Kodu Yazarken Dikkat Edilmesi Gerekenler

**Microsoft'a Özgü**

Kendi prolog ve epilog kod dizileri yazmadan önce, yığın çerçeve nasıl ortaya konulmuştur anlamak önemlidir. Önceden tanımlanmış **__LOCAL_SIZE** sabitin nasıl kullanılacağını bilmek de yararlıdır.

## <a name="cstack-frame-layout"></a><a name="_clang_c_stack_frame_layout"></a>CStack Çerçeve Düzeni

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

## <a name="the-__local_size-constant"></a><a name="_clang_the___local_size_constant"></a>__LOCAL_SIZE Sabiti

Derleyici, işlev prolog kodunun satır İçi assembler bloğunda kullanılmak üzere sabit, **__LOCAL_SIZE**sağlar. Bu sabit, özel giriş kodundaki yığın çerçevesinde yerel değişkenler için yer ayırmak üzere kullanılır.

Derleyici **__LOCAL_SIZE**değerini belirler. Değer, tüm kullanıcı tanımlı yerel değişkenlerin ve derleyici tarafından oluşturulan geçici değişkenlerin toplam bayt sayısıdır. **__LOCAL_SIZE** sadece ani bir operand olarak kullanılabilir; bir ifadede kullanılamaz. Bu sabitin değerini değiştirmemeli veya yeniden tanımlamamalısınız. Örneğin:

```
mov      eax, __LOCAL_SIZE           ;Immediate operand--Okay
mov      eax, [ebp - __LOCAL_SIZE]   ;Error
```

Özel prolog ve epilog dizileri içeren çıplak bir işlevaşağıdaki örnek prolog dizisinde **__LOCAL_SIZE** kullanır:

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

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[Naked İşlevleri](../c-language/naked-functions.md)
