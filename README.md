# Manually-Validation-Laravel
Manually Validation with Manually Message Show





use Illuminate\Support\Facades\Validator;

public function store(Request $request)
{

$validator = Validator::make($request->all(), [
            'user_id' => 'required',
            'category_id' => 'required',
            'product_name' => 'required',
            'location' => 'required',
            'price' => 'required',
            'condition' => 'required',
            'description' => 'required',

        ],[
            'user_id.required' => 'The User id field is required',
            'category_id.required' => 'The Category id field is required',
            'product_name.required' => 'The Product Name field is required',
            'location.required' => 'The Location field is required',
            'price.required' => 'The Price  field is required',
            'condition.required' => 'The Condition field is required',
            'description.required' => 'The Description field is required',
        ]);
        if($validator->fails()) {
            return response()->json(["status" => "failed", "message" => "validation_error", "errors" => $validator->errors()]);
        }
        
}

