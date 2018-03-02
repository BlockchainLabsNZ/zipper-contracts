# Dynamic Analysis

```
  Contract: PausableToken
    pause
      when the sender is the token owner
        when the token is unpaused
          ✓ pauses the token (63ms)
          ✓ emits a paused event (38ms)
        when the token is paused
          ✓ reverts
      when the sender is not the token owner
        ✓ reverts
    unpause
      when the sender is the token owner
        when the token is paused
          ✓ unpauses the token (48ms)
          ✓ emits an unpaused event
        when the token is unpaused
          ✓ reverts
      when the sender is not the token owner
        ✓ reverts
    pausable token
      paused
        ✓ is not paused by default
        ✓ is paused after being paused (43ms)
        ✓ is not paused after being paused and then unpaused (73ms)
      transfer
        ✓ allows to transfer when unpaused (66ms)
        ✓ allows to transfer when paused and then unpaused (122ms)
        ✓ reverts when trying to transfer when paused (50ms)
      approve
        ✓ allows to approve when unpaused (47ms)
        ✓ allows to transfer when paused and then unpaused (101ms)
        ✓ reverts when trying to transfer when paused (47ms)
      transfer from
        ✓ allows to transfer from when unpaused (68ms)
        ✓ allows to transfer when paused and then unpaused (120ms)
        ✓ reverts when trying to transfer from when paused (47ms)
      decrease approval
        ✓ allows to decrease approval when unpaused (46ms)
        ✓ allows to decrease approval when paused and then unpaused (108ms)
        ✓ reverts when trying to transfer when paused (45ms)
      increase approval
        ✓ allows to increase approval when unpaused (46ms)
        ✓ allows to increase approval when paused and then unpaused (102ms)
        ✓ reverts when trying to increase approval when paused (48ms)

  Contract: ZipToken
    ✓ should return the correct totalSupply after construction
    ✓ should return the correct allowance amount after approval (44ms)
    ✓ should return correct balances after transfer (61ms)
    ✓ should throw an error when trying to transfer more than balance (71ms)
    ✓ should return correct balances after transfering from another account (94ms)
    ✓ should throw an error when trying to transfer more than allowed (43ms)
    ✓ should throw an error when trying to transferFrom more than _from has (89ms)
    ✓ should increase by 50 then set to 0 when decreasing by more than 50 (73ms)
    ✓ should throw an error when trying to transfer to 0x0
    ✓ should throw an error when trying to transferFrom to 0x0 (43ms)
    validating allowance updates to spender
      ✓ should start with zero
      ✓ should increase by 50 then decrease by 10 (89ms)

  Contract: TokenVesting
    ✓ cannot be released before cliff
    ✓ can be released after cliff (175ms)
    ✓ should release proper amount after cliff (289ms)
    ✓ should linearly release tokens during vesting period (740ms)
    ✓ should have released all after end (180ms)
    ✓ should be revoked by owner if revocable is set (54ms)
    ✓ should fail to be revoked by owner if revocable not set (66ms)
    ✓ should return the non-vested tokens when revoked by owner (226ms)
    ✓ should keep the vested tokens when revoked by owner (215ms)
    ✓ should fail to be revoked a second time (210ms)

  Contract: ZipToken
    ✓ should put 1000000000 ZIP in the owner's account.
    ✓ should distribute all tokens.
    ✓ should fail to distribute too many tokens.


  51 passing (11s)

```
